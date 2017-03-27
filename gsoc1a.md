Front Desk Service Module / Experience Module -

Android App Development

**                                                         **

**                                                           ****Project Idea**

Mifos has recently released a full set of API’s to provide direct control of data to the clients.

Earlier there were bank facing API’s which were utilised in the Mifos web app and Mifos android

client as well as self-service app. Mifos android client helped the bank staff to access client’s

data on the go, but when it comes for booking a loan the customer interaction is very

unprofessional because the customer’s details like his background , the reason for which he

needs the loan , etc , are the deciding factors to match the personalized factors to the loan

products. With the help the API’s, I propose to develop a Front Desk Service Android App so

that there is a professional interaction with the organisation and the customer gets his/her loan

Product.

**                                                         Project Goals**

The goals which I aim to complete before the end of GSOC programme are as follows :

● Providing a way to check the credit history of the borrower and also the cash flow from

the customer’s business operations.

● Providing a login screen.

● Providing a client interface so that they can submit their basic requirement.

● Providing an interface which the contains a few personality based questions according to

which the machine can suggest a product.

● Provide an interface to help the customers edit their account information.

● Keeping record of customer’s loan transactions.

● The application will be having an offline support so that customers can see their loan

details even in areas with low or no network connectivity.

● Creating an application which is easy to use for clients , as there will be a large variety of

users ranging from qualified personals to not-so-qualified people, so I would try to make

the app easy to use.

● Providing labels and titles in regional languages.

**                                                         **

**                                                          The Project**

Front Desk Service Android App will be made from scratch so I will be trying to cover in-depth

implementation with the help of this proposal. I will follow agile methodology and keep adding

new features and functionalities from time to time as suggested by my mentor.All the data will be accessed using self service API’s which are already available. All the API

responses will be in the form of JSON which will be fetched in our android app via making HTTP

requests which will be handled with the help of Retrofit library so that all requests occur in

background thread without blocking the UI interaction of application with user.

Since the app will have offline support for the usage of the app in various places which have

different connectivity strengths so I would see to it that :

● Users can check their recommended loan products.

We can implement the offline application support with the help of SQLite database which is

automatically inherited by android operating system. Once the user is logged in data will be

fetched from server and certain amount of useful content will be saved in SQLite database, so

that users can access without network connectivity.

I will be using Model-View-Presenter(MVP) pattern as my design pattern

**User Interface** :

● User interface is simple and attractive which is totally fit for target user group.

● Adhere to the latest Android material design pattern that synthesizes the classic

principles of good design providing flexible and optimize layouts.

● User interfaces are designed for the different screen resolutions (MDPI, HDPI,

XHDPI,XXHDPI) which enables accessibility through all kinds of devices different

resolutions.

**Third party API’s/Libraries** :

● **OkHttp** : The application will be using extensive network calls to fetch data from the

server. OkHttp will provide automatic scheduling of network requests(HTTP based

network requests).

● **Retrofit** : Mifos X APIs are REST based and Retrofit is the best library to use in this

case.

● **Picasso** : For proper caching of images and also for preventing memory wastage in

heap.

● **Butter Knife** : Increasing readability of code.

● **GSON** : Serialization of java objects into JSON and vice versa.

● **SQLCipher** : Will protect the SQLite tables from reverse engineering attacks.

**Additional features** :

      ●    Feature to add documents such as ID proof or driving license.

      ●    Since there can be a lot of loan products based on customer’s details and questionnaire, I              would like to group the products according to their categories.

      ●    The loan products specifications will be elaborated so that the customer can take his

            time to decide which product to buy.

* Suppose there are multiple items for a specific customer according to the

            recommendation engine, the customer can have a wishlist to put the other products

            other than the product he selected, in it.

* Since the application will be used by different clients from different background, I would

            like to add a "how to guide", which will tell the clients how to use the various

            functionalities of the application.

During the whole development phase , continuous integration will be used. For that purpose we

will be using Travis CI as our continuous integration service.

**                                                     Project Timeline**

GSOC is around 4 month programme with three months to code, I would like to divide my tasks

into several phases.

● *Post proposal submission period*

            while ( 27/02/2017 <= time <= 20/03/2017 ) {

                      /* execute -> Working on submitting patches by resolving bugs

                         execute -> adding new feature to existing self service app */

                     }

● *Community Bonding Period*

            while ( 05/05/2017 <=time <=30/05/2017) {

                      /* I will be having my end semester examination from 25th March to 6th

                      May, so I won’t be available during this period.*/

                      while( 7/05/2017 <=time<=30/05/2017) {

                      /* execute -> Discussing key features with mentors such as :

                      > Proposed additional features should be implemented or not.

                      >Thoroughly reading MIFOS API documentation.

                      > Understanding and discussing about the features / code

                       Reusability of existing bank staff facing applications

                      > Implementation of MVP model in our application. */

                            }

                 }

● *Week 1*

            while (30/05/2017 <= time<=06/06/2017) {

                  /* execute -> Designing static UIs for example home screen,profile

                  screen,questionnaire screen,account-detail screen */

               }

● *Week 2*

              while (07/06/2017 <=time <=14/06/2017) {

                      /* execute -> Designing as well as writing code for navigation drawer.

                         execute -> Writing Code for collecting customer basic requirement.*/

                   }

●*Week 3*

             while (15/06/2017 <=time <=21/06/2017) {

                  /*execute -> Writing Code for adding recycler view in loan product screen.

                    execute -> Writing code for a login screen.*/

               }

● *Week 4*

            while (22/06/2017 <=time<=30/06/2017) {

                 /* execute -> Start writing backend logic for creating various service interfaces

                used for fetching data via Retrofit library.

                execute -> Writing code to populate data on the profile screen.

                execute -> submitting the code for phase 1 evaluation

               }

●*Week 5*

           while (01/07/2017 <=time <=08/07/2017) {

                /*execute -> Build profile screen in such a manner where user can edit only

                 specific fields.

                execute -> Writing code to provide editing profile options to the client.*/

              }

●*Week 6*

          while (09/07/2017 <=time <=16/07/2017) {

               /*execute -> Writing code for personality based questions*/

              }

●*Week 7*

          while (17/07/2017 <=time <=24/07/2017) {

              /*execute ->writing the code for loan products screen

                execute ->submitting the code for phase 2 evaluation*/

           }

●*Week 8*

        while (25/07/2015 <=time <=01/08/2015) {

            /*execute ->writing the code for offline support for application*/

          }

●*Week 9*

        while (02/08/2017 <=time <=09/08/2017) {

          /*execute -> Implementing loan transaction details functionality , where users

          can see details of their last loan transactions.*/

        }

●*Week 10*

       while(10/08/2017 <=time <=17/08/2017) {

        /*execute ->Writing test cases and start testing my final code.*/

       }

●*Week 11*

      while(18/08/2017 <=time<= 21/08/2017) {

        /*execute -> Writing the documentation of my entire work in a very detailed

          manner so that new contributors can easily contribute to my work*/

     }

So, I have left a few days as a carry period so that if anything goes unplanned we can use the

time to recover it and also I have mentioned a few tasks in some weeks as compared to other

for the same reason, so as to keep a check of my work. I will also add "how to use" in the app.

**Why are you the right person for this project?**

I consider myself as right person to do this project because :

● I learnt about this programme about a year ago, till then I had a little knowledge about

android and it’s features, but after knowing about the project I worked hard to improve

my skills on Android app development, so I am a fast learner and also a hard worker.

● Experience of programming in java for more than 2 years and development of android

app for a year.

● Contributed to Self-service app.If in college which area of study?

I am currently in my 3rd year Bachelor of Technology in Computer Science at National Institute

of Technology,Silchar, India.

Contact information and preferred method of contact

Email : [pritommaumdar1995@gmail.com](mailto:pritommaumdar1995@gmail.com)

Gitter ID : Pritom14

Contact Number : +91-7896223872/9707153020

Time Zone : Indian Standard Time (IST),+5:30 GMT

Linkedin ID :[ https://www.linkedin.com/in/pritommazumdar](https://www.linkedin.com/in/pritommazumdar)

I am available 24*7 via email as well as contact number

**Link to source code I have written/project developed**

I have recently learned android app development so I do not have a lot of apps developed in my

github profile, just two. But since GSOC provides a platform for learning so I could develop more

apps in future.

To-Do List App : [https://github.com/Pritom14/ToDoApp](https://github.com/Pritom14/ToDoApp)

Navigation App : [https://github.com/Pritom14/NavigationApp](https://github.com/Pritom14/NavigationApp)

These are the apps that I have developed.

**Have you contributed to other open source projects? If so, which?**

Yes, I have contributed to Self-Service App

**Have you any previous experience with JavaScript/Java/Spring/Hibernate/MySQL?**

I have programming experience of 2 years in Java. I also have past working experience

with MySQL. Since I will be working on the Front Desk Service App , for that I have a working

experience of a year in learning and developing android application.

**What other commitments do you have this summer?**

I do not have any other commitments this summer and I will devote my full time in

working on this project only. I will work for a minimum of 45 -50 hours/week, and also additional

hours for improving my skills.

**Have you deployed and run the Mifos X Platform and reference User Interface ?**

Yes

**Have you submitted any patches or source code to Mifos X yet?**

I have contributed to Self-Service App and the contributions are :

[https://github.com/openMF/self-service-app/pull/178](https://github.com/openMF/self-service-app/pull/178)[Merged]

[https://github.com/openMF/self-service-app/pull/138](https://github.com/openMF/self-service-app/pull/138)[Merged]

[https://github.com/openMF/self-service-app/pull/118](https://github.com/openMF/self-service-app/pull/118)[Merged]

**Have you previously participated in the Google Summer of Code?**

No

**Are you applying to multiple organizations this year?**

No

**Career Goals :**

● To become a successful android developer

● To bring a change in the lives of many , in technology , so that people can live a life with

ease, and so contributing to open source has been one of my goals.

