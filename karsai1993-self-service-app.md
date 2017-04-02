**Mifos Initiative:  Self-Service - Android App Version 2.0**

**László Karsai**

**Who am I? What do I study? Interests**

I am László Karsai from Budapest, Hungary. I attend Budapest University of Technology and Economics where I study Mechatronics. This field of technology collect and use the advantages of three individual fields: computer science/informatics, mechanics and electronics. As for me, the biggest impression has been caused by the computer science ever since I wrote my first working program. I thought to myself "How great it is that I can see the result of my work on the screen". I started to write codes in C/C++ but a little time later I began to use Java program language. When I got my first smartphone, I started to think about how the programs which I run are built and structured, and how the program codes of them look like. I had opportunity to participate in an Android software development course in the university. I liked it so much and I was excited to create my first application. This was the point when I knew that I would have to become a software developer. Besides my home-made projects being coded in C/C++, Java and Android program languages, I started to work as a software developer in the aviation industry where I managed to extend my experiences with python, bash and MySQL. I have always liked being challenged because it is such a good feeling to solve issues. I am here to continue to gain experiences and to make the Self Service application better and better so as to help people who use it. 

**Contact information and preferred method of contact**

Email address: karsai1993@gmail.com

Gitter ID: karsai1993

Skype ID: karsai1993

Telephone number: +36 30 484 2239

Time zone: CEST

My preferred method of contact is email but if we schedule a time period, we can get in contact via telephone or skype.

**Project idea and goals**

The current version of the application contains a full set of client-facing APIs to enable self-service channels for clients to interact with their own data and transact in a self-service manner. As of now, clients can authenticate themselves, view and edit their account details and make repayments or transactions between their own accounts. The goal of my work is to create the 2.0 version of the application which contains some exciting features and modifications in order to extend the existing self-service RESTful APIs. I describe them all in the followings:

* Application-wide UI improvement - After finding the Self Service Application (and this project), I could very quickly get familiar with the application and its use cases. I have recognized some issues but most of them relates to the UI part of the application. I think it is important for the application to have a good look. It can increase my efficiency as I know that I would be able to perform a more successful work with an application which is both nice and well-coded. 

* Registering/signing up process - It is important to have a process in which the customers can register/sign up into the application and have a look at their own accounts.This feature would contain an administrator user and a validation process. Through this validation process, the customer login user’s data get validated by the administrator user. I have been thinking of it for days, this is my idea: Validation would be required for the user to be able to do special actions. E.g: third party transfer, but I think it should be discussed in the community bonding period. After the customer login user fills all the required data fields, she/he is able to validate it by sending a request to the admin user. There would be an activity for the admin user to have a look at checkboxes of all the users and simply check the certain user who should be validated. After this, the user is valid and can make the previously banned actions, too.

* Customer login users as individual users - Every customer login user should see only their own accounts data. This should be solved by detecting the user’s id which is delegated to the user at the registration entry. We should avoid making users be able to see the others data except the cases when it is a demand (see: third party account transfer below)

* Third party account transfer - It is also a challenging feature to make the users able to send their certain data to another user(s). I image it this way: all the accounts relating to the certain user are listed. The user can click on one of them which results in to open a new activity. In this activity, there would be a button texted as "Share". After clicking it, the user should identify the user(s) she/he would send that certain account. After sending it, the operation should be done in database containing the accounts.

* First steps wizard - This would be a new feature: after running the application for the first time, it was not clear how to start using that. And I think this should be fixed by some helping words when the user enters into an activity about what she/he can do in that activity and where she/he can continue the workflow. This significance of this feature according to the point of view of Mifos organization should be discussed.

* Mobile wallet integration - The point of my implementation regarding this would allow the user to instantly, easily, and cost-effectively offer an outstanding customer experience to increase loyalty to the application or maximize savings and loans related transfer money distribution. It requires further discussions after the student selection. I escalate it a one-week job but if it requires more, I am totally open for it and willing to try to make the other parts of my goals faster to handle this integration.

* Unit and integration test - It should fluently be performed besides coding, but before the final evaluation, it is important to test the whole concept of the application because it is very important for every part of it to work fine and to be ready for the release of the 2.0 version.  

**Time schedule of implementation**

In this schedule, I write about my plans for the community bonding period and my workflow in the coding period. My workflow would be divided into three parts according to the evaluations. My work would include high quality User Experience based on the Android Style. I have three months to perform the goals above and it is enough time for me to do so with quality. My time schedule can be seen below.

1. **Before the coding period (community bonding period)**

It is very important to get the application well-designed. There are some pending issues reported by me regarding UI. I would take this time period to finish the UI upgrade of the application. And of course, this period would give me opportunity to get to know the mentors I would work with during the summer and the application deeply focusing on parts where my goals can be implemented. 

**Deliverables: Complete UI of the application which meets the requirements of  Android Style and mentors**

2. **Before the first evaluation**

May 30 - June 4: Creating register/sign in related activities and resources (User Sign Up part one).

June 5 - June 11: Creating an admin user who has all the rights to update, change the customer login user and to deactivate if needed. In addition, the Administrator should be able to assign certain permissions to the customer login user so as to control the actions she/he can perform. Testing the available actions/views of administrator user and customer login user (User Sign Up part two).

June 12 - June 18: After signing in, the customer login user should fill a form which ask her/him about his basic information e.g.: email address. She/he would be able to decide to choose a profile picture and change her/his password (User Details Feature and Update User Details).

June 19 - June 26: Creating validation process between the user and the organization through the user’s personal data.

June 27 - June 30: Period of closing this section (final tests and starting documentation) and submitting Phase 1 evaluation.

**Deliverables: Register/sign in process, admin user and customer login user information processing, validation process**

3. **Before the second evaluation**

June 30 - July 5: Creating user’s input process and queries (to display only the certain customer login user related data) regarding to retrieving list of her/his savings accounts details, transactions and charges to the savings accounts.

July 6 - July 12: Creating user’s input process and queries (to display only the certain customer login user related data) regarding to list of her/his loan account details, transactions, repayment schedule and charges of each loan account.

July 13 - July 19: Creating update and withdraw process of loan application

July 19 - July 25: Implementing third party account transfers

July 25 - July 28: Period of closing this section (final tests and continuing documentation) and submitting Phase 2 evaluation.

**Deliverables: User input handling (savings and loan related details, transactions and charges), update and withdraw possibilities of loans, third party account transfers**

4. **Before the final evaluation**

July 28 - Aug. 6: Creating user wizard which would help the user(s) who freshly signs in the application to get a brief explanation about the functions of application and how she/he(they) can use it. This wizard is planned to be available if the user(s) would like to have a look at it again.

Aug. 7 - Aug. 13: Mobile wallet integration. The time of performing this can be extended with extra time depending on the discussion about the exact goals after the student selection (API and mockups). 

Aug. 14 - Aug. 20: Unit and integration test of the whole application focusing on my deliverables

Aug. 21 - Aug. 29: Period of closing the final section (finishing documentation) and submitting the final evaluation.

**Deliverables: User wizard, mobile wallet integration, unit and integration tests for release**

**Motivation**

I have always been willing to receive opportunities which inspire me to be a better software developer. During building the application and creating issues, I got more and more enthusiast about development for the Mifos Initiative open source organization because I felt excited during the my approaches of getting the application better and better. Since building and running the application for the first time, I have felt comfort and familiarity with it. I would like to continue my work in the summer as a GSoC participant. GSoC means for me an opportunity that I know I should not miss because ever since I read about it (last summer), I have known that it is the right commitment which makes me more project-orientated and gives me more knowledge about the process steps of the software development. As for Mifos organization, I really like the application and feel passion to improve it with the detailed features. 

**Career goals**

First of finishing the university with the most gained experiences which are available for me. After that I would like to go abroad to have international living and working experience. I have not pointed out a country where I would like to live so far. Sooner or later, I would like to be a senior software developer. I think it is one of the best position because you have responsibility and opportunity to help others by sharing your knowledge with them.

**Why I am the right person for this project**

The most important fact that using the application and solving issues made me more inspired to continue to work on it during the summer and after that. I have reported issues and solutions daily since I found this project among the other ones. I got really familiar with this type of workflow and realized that it suits me well. I used to say that there are no problems, only opportunities for better solutions. I am hardworking enough to keep giving my best and reach my goals. Besides it, I have gained relevant, professional coding experiences for 5-6 years in different languages, mostly Android and Java. Additionally, I like the challenges and being challenged because I can learn/work fast and efficiently and am willing to do so in order to fulfill the expectations against me. Last but not least, the UI of the applications, which I develop, are very important for me because a good UI would make me more productive as I can see that I have done so far fit in the application well.

**Source code I have written**

I started to write an application for Android smart phones to pay attention better on my expenses. The name of it is Expense Observer. Here is the link for my GitHub repository created for this project: [https://github.com/karsai1993/expense_observer](https://github.com/karsai1993/expense_observer).

**Contribution to open source projects**

The open source projects I have contributed to:

* openMF/self-service-app ([https://github.com/openMF/self-service-app](https://github.com/openMF/self-service-app))

As soon as I could run the application on my phone, I could realizes some issues, reported them. I have already solved all of them. I tried to explain the problems in each cases to make it understandable via text and/or screenshots. When I made a solution, I created screenshots to prove that the problem is gone. Pull request is created.

* openMF/android-client ([https://github.com/openMF/android-client](https://github.com/openMF/android-client))

I have recognized issues and solved them on the same way as written above. My pull request was approved and merged. From that time, I reported some further issues.

* k9mail/k-9 ([https://github.com/k9mail/k-9](https://github.com/k9mail/k-9))

	I have reported some issues.

**Experiences**

I have gained experience with:

* Android - home made projects and open source organization

* Java - working experience, home made projects, homeworks

* bash - working experience

* python - working experience

* Javascript - final project in BSc

* C/C++ - Arduino, home made projects, homeworks

* MySQL - working experience, homeworks

**Commitments in the summer**

 I have a part-time job in IT company being in the aviation industry. I think it does not sound well from your point of view but please, note the followings:

* my working time is flexible, so I can work when I want

* As I can work fast and efficiently, in the last week, I had enough time to get deeply into the MifosXDroid and Self Service App applications, reporting issues, solving problems besides my job, so this would not be a problem in the summer, either.

* I can work in this project at least 5 hours a day in the week and 8 hours a day in the weekend which is 41 hours.

Please note, that the Summer of Code would be my first priority in this summer because I think it is a significant opportunity to learn and get better.

**Platform and reference User Interface**

Yes, I have cloned the original one, I have not created a fork from either of them so far.

**Submitting patches and source code to Mifos X**

Yes, I have submitted several ones. Here is the list:

* openMF/android-client

1. Fix: EditText hint text is fully readable

[https://github.com/openMF/android-client/pull/580/commits/d1d46acbac3f4d830001d03ddeada121437deeae](https://github.com/openMF/android-client/pull/580/commits/d1d46acbac3f4d830001d03ddeada121437deeae)

2. Fix:Items in option menu are always shown,handled

[https://github.com/openMF/android-client/pull/580/commits/ea75872283d963b6b69758cd1359bc4ee6e04531](https://github.com/openMF/android-client/pull/580/commits/ea75872283d963b6b69758cd1359bc4ee6e04531)

* openMF/self-service-app

1. Fix: Transaction option menu button is disabled

[https://github.com/openMF/self-service-app/pull/208/commits/6ca80b823f294fad62b7c0ab667188e3273854af](https://github.com/openMF/self-service-app/pull/208/commits/6ca80b823f294fad62b7c0ab667188e3273854af)

2. Refactor: Improve UX and use thousands separators

[https://github.com/openMF/self-service-app/pull/208/commits/efd96cbd08c3c8e05a20eb3e5f6470418cc46c86](https://github.com/openMF/self-service-app/pull/208/commits/efd96cbd08c3c8e05a20eb3e5f6470418cc46c86)

3. Refactor: Change colors of status of Approved and other

[https://github.com/openMF/self-service-app/pull/208/commits/ded3285737d006235e3fbf1b799d9437239cd84f](https://github.com/openMF/self-service-app/pull/208/commits/ded3285737d006235e3fbf1b799d9437239cd84f)

4. Fix: Set the English language as default locale

[https://github.com/openMF/self-service-app/pull/208/commits/275cced0b4f49ab26b82c513c8401aea3ccaafbd](https://github.com/openMF/self-service-app/pull/208/commits/275cced0b4f49ab26b82c513c8401aea3ccaafbd)

5. Refactor: Change code according to code style requirements

[https://github.com/openMF/self-service-app/pull/208/commits/335bbb5b6419c70b6c1849db40d6a1bf47dc11e3](https://github.com/openMF/self-service-app/pull/208/commits/335bbb5b6419c70b6c1849db40d6a1bf47dc11e3)

6. Fix: Improve thousands separator process

[https://github.com/openMF/self-service-app/pull/208/commits/5bec9410384b4ea852297a02441739ecb70ae4c1](https://github.com/openMF/self-service-app/pull/208/commits/5bec9410384b4ea852297a02441739ecb70ae4c1)

**Taking part in Google Summer of Code**

Unfortunately, no, I have not participated in it so far.

**Applying to multiple organization**

Yes, I plan to apply to multiple ones. As of Mifos Initiative, I would like to apply to the Android Field Operations App Version 4 project, too. So in this organization, there are two projects which grabbed my attention.

Mifos Initiative is definitely my first choice. I am happy to have found it among a lot of organizations. 

