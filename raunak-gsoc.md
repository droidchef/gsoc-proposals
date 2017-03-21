Self Service Web Application

Raunak Sett

( [sett.raunak@gmail.com](mailto:sett.raunak@gmail.com) )

# Project Idea

## Overview 

The Self service web application allows end users to interact with their own data such as view pending payments or make transactions to their existing loans and transfers. Mifos has already released the set of APIs needed to finish the self service web app and I propose to develop this application which will result in removing a certain amount of dependency for the clients and they can have direct control as allowed by admins and be self functional themselves.

## Goals

The set of requirements that the self service web app would require to fulfill are as follows: 

* Users are able to authenticate themselves. 

* Users get a dashboard for an overview of all their transactions and savings.

* Users are able to view their profile and update it.

* Users are able to view their accounts.

* Users are able set up beneficiaries for themselves with limits.

* Users are able to make transactions if they have the permission such as

    * Initiating Transfers

    * Repayment

* Users are able to fill up questionnaires

* Users are able to view loan products

* Users are able to request for other services such as initiating a deposit, submission of a form or documents for loan products.

* A responsive web app is required to cater to all kinds of devices. 

* The nature of the user using the self service web app may vary, therefore the user experience needs to good. It should be intuitive for the end user to navigate and use. 

* The previous point also arises the need for multi lingual support of the application as with the community app. Assets for other languages may be added iteratively. 

# Implementation

The application would be created from scratch so I’ll provide as specific technical details that I am proposing for the self service web app. I’m providing the technical specifications to the best of my ability along with the reasoning with my best knowledge. This specification might undergo multiple revisions per further discussions with mentor(s).

## Directory Structure

Following is proposed directory structure for the angular app 

.

├── app

│   ├── core

│   │   ├── core.config.js

│   │   ├── core.module.js

│   │   ├── core.run.js

│   │   ├── directives

│   │   │   ├── coreDirective1

│   │   │   │   ├── coreDirective1.directive.js

│   │   │   │   └── coreDirective1.scss

│   │   ├── filters

│   │   │   ├── coreFilter1.filter.js

│   │   │   └── coreFilter2.filter.js

│   │   ├── layouts

│   │   │   ├── content-only.html

│   │   │   ├── content-with-toolbar.html

│   │   ├── scss

│   │   │   ├── global.scss

│   │   │   └── partials

│   │   │       └── helpers.scss

│   │   ├── services

│   │   │   └── core-service.service.js

│   ├── models

│   │   ├── component1

│   │   │   └── model1.json

│   ├── main

│   │   ├── toplevelcomponent

│   │   │   ├── toplevelcomponent.module.js

│   │   │   ├── childcomponent1

│   │   │   │   ├── childcomponent1.controller.js

│   │   │   │   ├── childcomponent1.html

│   │   │   │   ├── childcomponent1.module.js

│   │   │   │   ├── childcomponent1.scss

│   │   │   │   └── i18n

│   │   │   │       ├── en.json

│   │   │   │       └── es.json

│   │   └──  main.controller.js

│   ├── index.api.js

│   ├── index.config.js

│   ├── index.constants.js

│   ├── index.controller.js

│   ├── index.module.js

│   ├── index.route.js

│   ├── index.run.js

│   ├── index.scss

├── index.html

├── assets

└── favicon.ico

### Motivation

The motivation behind this directory structure is to decouple each individual module of the application into a pseudo mini app. The core application is separated from the sub modules. Each modules can have dependent modules which can be used. This also allows to scale the application and collaboration easier. People can work on individual modules from modifying controller logic to view implementations. Folders are grouped according to features. This directory structure follows the LIFT pattern.

1. Locating the code is easy

2. Identify code at a glance

3. Flat structure as long as we can

4. Try to stay DRY (Don’t Repeat Yourself)

[Ref [https://johnpapa.net/angular-app-structuring-guidelines/](https://johnpapa.net/angular-app-structuring-guidelines/) ]

## Design Specifications

I’ll be using Angular Material for UI components, that is material design for the user experience. All extra extending stylesheets would be written in **sass**. Mockups would be created on **sketch** so stylesheets are easier to import from design and the workflow of coding up the frontend is faster.   

## Mockups

I’ve tried and setup a basic theme for the self service web app. These can be iterated over and improved over with feedback. I’m attaching the mockups of the core functionality, I’ll be uploading all mockups of all the screens on Google drive. Please Click **[Here](https://drive.google.com/open?id=0B4U0K0qlaWsyV2w2bGlwSVpfUlk) to view all mockups.

Login and Dashboard

## Data Access

The web self service app has almost all the APIs setup for the functioning of the core features to function. We might need more APIs depending on the extra features that we add on the self service web app. As per the documentation we might need more apis for features such as initiating transfers, requesting for document collection or opening of savings account. Only `GET` methods are allowed as of now for full functionality more endpoints would be required. Therefore the features would have been created a rest hookup call is what would be required in the end. The timeline would try to accommodate as many goals of the self service in the timeline through stubbing responses etc. So later they can be hooked up to the api and are ready for deployment.  

[ Ref [https://cwiki.apache.org/confluence/display/FINERACT/Customer+Self-Service](https://cwiki.apache.org/confluence/display/FINERACT/Customer+Self-Service) ]

## Build System

For this project I will be using **gulp** as the build system to compile sass, building the angular code. Making a production build etc. 

## Quality Assurance

For any product this is of utmost important to make sure that quality is ensured, below are ways in which I will ensure that the product quality is maintained. 

### Code Quality

Code quality can be ensured by following the Angular Style Guide from John Papa, with comments and documentation created during the development. Documentation of the code happens parallely with development for easier future collaborations. Also **eslint **would be setup for the project for linting purposes.

[ Ref [https://github.com/johnpapa/angular-styleguide/tree/master/a1](https://github.com/johnpapa/angular-styleguide/tree/master/a1) ]

### Testing

I will follow a test driven approach and unit test specifications for the view would be setup before development and made sure that all tests are passing the end of development. I will be using **jasmine** for testing the functional parts of the angular application.

If the timelines go accordingly, and everything is perfect in the buffer period, See project timeline for further details, I will try to incorporate end to end tests (**e2e**) using **protractor**

### Continuous Integration

The self service web app would be hooked up to Travis CI. Making sure that the codebase maintains the standards defined in quality assurance.

## Timeline

### Post proposal Submission [ 21st Mar - 10th Apr ] 

* Further Submit patches to the community-app.

* Further discussions on the details in the proposals and updation if required.

* Fix Issue #1820 [Ref [https://github.com/openMF/community-app/issues/1820](https://github.com/openMF/community-app/issues/1820) ] to create the base for the self service web app so users could be added [if remains unsolved].

* Iterate on wireframes, make design decisions on feedback. 

* Actively interact with the community.

### Community Bonding [ 5 May to 30th May ]

I’m in my final year, so I’ll be having my exams till 23rd May So I’ll be busy during that period. I’ll be actively available and discussing in the post proposal submission period.

#### [ 24th May - 30th May]

* Actively bond with the community

* Finalize the design specifications, UI and flows. 

* Finalize the specifications for the web app.  

### Coding Period

#### Week 1 [31st May - 6th Jun]

* Setting Up the Base Layouts, Navigation, Login, Toolbar, etc

* Build the core angular app specifying directory structure

* Setting up the build system. [Gulp]

* Setup Multi Language support

#### Week 2 [7th Jun - 14th Jun]

* Complete The Authentication Module

* Complete the unit tests for this feature

* Start creating static UI screens (HTML and SASS)

#### Week 3 [15th Jun - 21st Jun]

* Create all static UIs for all screens in mockups.

#### Week 4 [22nd Jun - 29th Jun]

* Code Profile View and Updation.

* Complete Unit tests for this feature

* **Evaluation [ 26 th Jun to 30th Jun ]**

#### Week 5 [30th Jun - 6th Jul]

* Code View Accounts and Transaction

* Complete Testing for both

#### Week 6 [7th Jul - 14th Jul]

* Code Browse Available Loan Products

* Complete Testing

#### Week 7 [15th Jul - 21st Jul]

* Code Users able to browse and add beneficiary

* Complete Testing

#### Week 8 [22nd Jul - 29th Jul]

* Code Make Transfers to other accounts

* Test the Code

* **Phase 2 Evaluation [ Jul 24 - 28th ]**

#### Week 9 [30th Jul - 5th Jul]

* Code Feature to Submit a loan application

* Update or Delete the loan application

* Complete Testing

#### Week 10 [30th Jul - 5th Aug]

* Code Fill up questionnaire screen

* Complete Testing

#### Week 11 [6th Aug - 12th Aug]
Week 12 [13th Aug - 20th Aug]

I’m keeping the final 2 weeks as the final project buffer period where in if somethings goes unplanned in the timeline I’m able to deliver a complete finished product. Else I will use these weeks to code up some more value addition features for the web self service if possible.

# Questions

### Why are you the right person for this project?

I believe myself to be the right person for this project is because 

* I’ve volunteered for Non profits providing solutions through tech for the needy and I am motivated to the cause and purpose that mifos stands for. 

* I’ve contributed actively resolving issues on the community app, so that experience will help apply the mifos standards and knowledge to this project as well

* I have past experience in developing angular apps, plus I believe in shipping products that create value which drives me. 

* I also have worked as a designer, So I’ll be able to apply my knowledge of design to this project which will only enhance the experience

### If in college, current area of study?

I’m currently studying at Bhaskaracharya College of Applied Sciences ( University Of Delhi ). I’m currently in my 4th (Final) Year and pursuing a degree in Bachelor in Technology in Computer Science. 

### Contact Information and preferred method of contact

Name: Raunak Sett

Email: [sett.raunak@gmail.com](mailto:sett.raunak@gmail.com) (Preferred)

Skype Id: raunak.sett

Telephone Number: +91 8800544186

GitterID: botraunak

Time Zone​: Indian Standard Time (IST),+5:30 GMT

### Career Goals

I want to be a front end engineer. And develop client side impact oriented mobile and web applications. I love creating products that might solve a bigger a problem for a lot of users. I also have a keen interest towards design. 

### Please share any links to source code you have written or websites you have built?

I have worked on multiple projects throughout my college years as internships. Most of them are closed source, I shall list a few of the past experiences I’ve had: 

Swasthya Lehar:

A non profit working towards improving the healthcare scenario of the urban poor of India. I worked on the product ‘**Barefoot Champs**’ an on ground data collection app (Hybrid App on cordova) for the internal use of organization to track individuals and connect them to hospitals. 

Watchlyst

I developed the Content Management System for their application from scratch and also did their website as a part of my summer internship. 

[http://watchlyst.com/#](http://watchlyst.com/#) 

Qustn Technologies

I worked on their Learning Management System’s hybrid app made on cordova and angular JS. I contributed for 2 months as an intern.

### If you have visited our Gitter chatroom, what nickname did you use?

Yes, I did visit the gitter chatroom. @botraunak

### Have you contributed to other open source projects? If so, which?

No, I was recently introduced to open source development.

### Have you any previous experience with JavaScript / Java / Spring / Hibernate / MySQL?

Yes I have previous experience in Javascript and MySQL. 

I’ve been learning javascripting and doing small / big (internships) projects since first year. 

### What other commitments do you have this summer? (working on this project is a full-time job and must be your primary commitment!)

Other than volunteering for a non profit on weekends / extra time I don’t have any active commitments this summer. 

### Have you deployed and run the platform ([https://github.com/openMF/incubator-fineract](https://github.com/openMF/incubator-fineract)) and reference User Interface ([https://github.com/openMF/community-app)?](https://github.com/openMF/community-app)?)

Yes I have deployed and run the platform, and worked on the community app.

### Have you submitted any patches or source code to Mifos X yet? Please provides links to the commit in GitHub or the JIRA ticket (students looking to be seriously considered should make at least one submission)

Yes I have 12 merged pull requests on the community App.

1. [https://github.com/openMF/community-app/pull/2009](https://github.com/openMF/community-app/pull/2009)

2. [https://github.com/openMF/community-app/pull/2013](https://github.com/openMF/community-app/pull/2013)

3. [https://github.com/openMF/community-app/pull/2058](https://github.com/openMF/community-app/pull/2058) 

4. [https://github.com/openMF/community-app/pull/2059](https://github.com/openMF/community-app/pull/2059)

5. [https://github.com/openMF/community-app/pull/2071](https://github.com/openMF/community-app/pull/2071) 

6. [https://github.com/openMF/community-app/pull/1964](https://github.com/openMF/community-app/pull/1964) 

7. [https://github.com/openMF/community-app/pull/1978](https://github.com/openMF/community-app/pull/1978)

8. [https://github.com/openMF/community-app/pull/1984](https://github.com/openMF/community-app/pull/1984) 

9. [https://github.com/openMF/community-app/pull/1990](https://github.com/openMF/community-app/pull/1990) 

10. [https://github.com/openMF/community-app/pull/1997](https://github.com/openMF/community-app/pull/1997)

11. [https://github.com/openMF/community-app/pull/2001](https://github.com/openMF/community-app/pull/2001)

12. [https://github.com/openMF/community-app/pull/2007](https://github.com/openMF/community-app/pull/2007)

### Have you previously participated in the Google Summer of Code?

No, This is my first time participating in Google Summer of Code

### Are you applying to multiple organizations this year?

No, Mifos is the only organization I’m applying to this year. 

