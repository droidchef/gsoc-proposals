**Polkit support in KIO**

*Name: Chinmoy Ranjan Pradhan*

*Email: chinmoyrp65@gmail.com*

*IRC Nick: chinmoy*

**INTRODUCTION**

KIO framework is used by KDE applications to provide file management abilities. This framework provides almost all file management functions that one will ever need. 

However it doesn’t provide any support for file management as a privileged user. So whenever there is a need to perform file management tasks with escalated privileges the application simply shows an error. A casual user may not see it as a problem but for power users, sysadmins, developers this is a huge impedance. Many users get around this by starting the whole application as root. Running Qt/KDE GUI applications as root is not only sub par but also a very dangerous solution. Dangerous because if not handled properly it can cause irreversible damage to the the system. To address this issue some KDE applications are disabling being executed as root. For example, the next versions of Dolphin and Kate will show an error message and exit when started with root privileges.

The optimal solution to this problem is to perform only one specific action as root instead of giving root privileges to the whole application. Just here Polkit comes to rescue. Polkit is the standard framework used by Linux desktops to grant privileged actions to unprivileged processes. 

The goal of this project is to add Polkit support in KIO. After this addition applications will be able to perform privileged actions after authentication. The behaviour post authentication will be similar to sudo command. This means for sometime the user can perform privileged tasks without entering the password repeatedly. However to prevent any accidental damage to the system a warning dialog will be shown prior to performing the task.

**DELIVERABLES**

Polkit support to the following file operations :

1. Delete

2. Copy/Cut

3. Trash 

4. Rename

5. Creating Symlinks

6. Creating New Files

IF time permits:

1.  Integration in dolphin

1. Relaxing assumptions in write protected locations.

2. Highlighting the context menu actions when they require privilege to execute.

3. Showing necessary warning before executing an action with privilege.

    

**IMPLEMENTATION**

I will implement the aforementioned behavior in following steps:

1. Adding necessary warnings

2. Adding KAuth Helper

3. Refactoring File Ioslave

4. Testing

*WARNING DIALOG*

A warning is displayed when an application tries to perform a privileged action during the persistence period. It is needed to prevent the application from doing any accidental damage to the system. The warning dialog is basically a KMessageBox and is shown as soon as insufficient privileges are detected. The warning will contain a message describing the cause of warning and the item(s) for which the warning is being shown.

The warning can either be shown from ioslave or from application through jobuidelegate. 

Showing it from ioslave provides us with greater control over the contents of warning but we may end up showing similar warning twice. Meanwhile showing warning from the application gives us control over the number of times the warning is to be displayed but on the flip side we have to stat the items which in some cases can be time consuming. As we see both the cases have their pros and cons. I will decide upon one of them during the initial period of gsoc.

*KAUTH HELPER*

KAuth helper is the utility that does the actual work. All the file management functions that require privileged execution are placed in this utility. An ‘execute’ method will be exposed over D-Bus. This will be called by the file ioslave when the need is there.

I will add number of actions to the helper utility which can be safely performed as a privileged user. These actions are listed below.

* Delete Function

1. del - deletes a file

2. rmdir - deletes a directory

* Copy/Cut/Trash Function

1. open - opens a QFile in write protected location

2. read - reads content of file

3. write - writes into a file

4. sendfile - to copy inside write protected location

5. close - close a QFile

6. chmod - sets the permission

* Rename Function

1. rename - to rename a file

* Creating New Files

1. get - get contents of file

2. put - put contents of a resource file into a local file

* Creating Symlinks

1. symlink - to create a soft link

*REFACTORING FILE IOSLAVE*

File ioslave performs all the file management task. At the moment file ioslave doesn't support performing action as a privileged user. It simply returns an error message when there is insufficient privilege. 

To solve this issue I will start by replacing error messages which are displayed when insufficient privilege is detected  by a call to method named ‘execWithRoot’. 

This call will be made with the name of action that requires privilege and the path of items upon which the action is to be performed as parameters. 

The work of ‘execWithRoot’ is then to prepare a QVariantMap containing the necessary data and call the kauth helper which will perform the action with escalated privileges. 

I have also planned to introduce warning dialog in this part of code but there’s also the possibility of the warning being shown from the application’s side. It all depends on the relative advantages and disadvantages of both the approaches.

I have a PoC patch which makes use of the above approach.The warning is shown from the ioslave. This patch can be found here [[3]](https://git.reviewboard.kde.org/r/129983/).

File ioslave has different methods responsible for different file management function. I will add support for polkit to one method at a time and in the following order:

* Delete Function

In linux the methods FileProtocol::del and FileProtocol::deleteRecursive combined are responsible for deleting files and directories. The former method deletes one file or one empty directory at a time. Whereas the later is called when directory is not empty. It then deletes all the items inside recursively. Currently when deletion of file/directory requires privilege this method shows an error and terminates the whole delete operation.

So to overcome this l will add the usual call to 'execWithRoot' which will take care of kauth related stuffs i.e. getting the action, preparing metadata, executing KAuth::Action and additionally show a warning.

Now it's the delete function where if we choose to show warning from ioslave we might end up showing a similar warning twice which is very unpleasant. And if we choose to show warning jobuidelegate we might slow down the whole delete operation

* Copy, Cut and Trash Function

These operations are performed by FileProtocol::copy because all are just special cases of copy. Performing any one of them with escalated privileges will require combination of call to the helper actions open, read, write, sendfile and the likes. 

As to showing warning dialog choosing between ioslave and jobuidelegate doesn’t really matter. Both the approach will show the warning once and won’t slow down the operation.

* Rename

It is performed by FileProtocol::rename. It is just a matter of few lines of changes before it can do privileged renaming. The helper action rename will be called for this task.

* Creating Symlink

To create symlink ioslave uses the FileProtocol::symlink method. A call to helper’s symlink action is required when creating symlink as a privileged user.

* Creating New Files

FileProtocol::get and FileProtocol::put along with FileProtocol::copy are used by KNewFileMenu to create new files. In both get and put method there’s only one place where execWithRoot needs to placed. Additionally there will be some changes to KPropertiesDialog as well because it is responsible for creating new desktop (.desktop) files.

*TESTING*

I will add unit tests in last couple of weeks. But still I will try to add unittest for a function as soon as I finish adding polkit support to it.

Meanwhile to manually test the changes I will make use of kioslavetest which is in KIO’s test suite. I have also prepared a small app specifically for this purpose. It’s a menu driven app which tries to mimics the file management menu of  dolphin. This can be found here [[4]](https://github.com/crp999/polkitintegrationtest).

*TENTATIVE TIMELINE*

* May

  Community Bonding Period

  Week 1: List out the parts of kio this project might touch.

  Week 2: Check whether to show warning from jobuidelegate or file ioslave. Compare the 

                pros and cons of each case.

  Week 3: Prepare necessary warning dialogs. Decide upon the message and data they need 

                to show.

  Week 4: Start adding relevent code for warning dialog.

 

* June

  Week 1: Work on kauth helper.

  Week 2: Work on kauth helper.

  Week 3: Finish work on FileProtocol::del and FileProtocol::deleteRecursive. The patch is up   

                for review here [[3]](https://git.reviewboard.kde.org/r/129983/).

  Week 4: Add polkit support to Copy/Cut/Trash function.

* July

  Week 1: Continue work on FileProtocol::copy.

  Week 2: Add polkit support to Rename and Symlink function.

  Week 3: Add polkit support in Creating New Files.

  Week 4: Connect everything i.e. ioslave, helper and warning dialogs.

* August

  Week 1: Add unit test and do manual testing.

  Week 2: Continue testing.

*OTHER OBLIGATIONS*

In the month of may I will be having my semester end exams. The exam will last for about a week. During those seven days I can only manage to work for 2-3 hours. And in august my college will reopen. During those two weeks I can manage upto 5 hours. I will compensate for this during my vacation. Except this I don’t have any other commitments.

*ABOUT ME*

I am a 1st year Computer Science student at Dr. Ambedkar Institute of Technology, Bangalore, India. I have been a KDE user for a year or so and a contributor for about 8 months. I am comfortable C/C++ and I have working knowledge of bash scripting and python.  I’ve submitted number of patches which can be found here [[1]](https://git.reviewboard.kde.org/users/chinmoyr/)[[2]](https://phabricator.kde.org/audit/?authors=chinmoyr). My contributions are predominantly to KIO so I am very much comfortable with its code base. I have also prepared a PoC patch which adds polkit support to the delete operation. This further strengthened my understanding of the parts of KIO this project involves.

*LINKS USED*

[1] : [https://git.reviewboard.kde.org/users/chinmoyr/](https://git.reviewboard.kde.org/users/chinmoyr/)

[2] : [https://phabricator.kde.org/audit/?authors=chinmoyr](https://phabricator.kde.org/audit/?authors=chinmoyr) [All of my submissions]

[3] : [https://git.reviewboard.kde.org/r/129983/](https://git.reviewboard.kde.org/r/129983/)  [PoC Patch]

[4] : [https://github.com/crp999/polkitintegrationtest](https://github.com/crp999/polkitintegrationtest) 

