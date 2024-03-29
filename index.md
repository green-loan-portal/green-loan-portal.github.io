## Table of Contents
* [Overview](#overview)
* [Milestone 1](https://github.com/orgs/green-loan-portal/projects/1)
* [Milestone 2](https://github.com/orgs/green-loan-portal/projects/2)
* [Milestone 3](https://github.com/orgs/green-loan-portal/projects/3)
* [Accessing the application on the web](http://simple-green-loans.meteorapp.com/#/)
* [User Interface Demonstration](#demo)
* [Community Feedback](#feedback)
* [Installation](#installation)
* [Team Members](#teammembers)

<a name="overview"></a>
## Overview

green-loan-portal is a web application that we have created for the [GEM$ loan program](https://gems.hawaii.gov/). The application provides improvements to the current process which is done manually and is very prone to errors. As of now, the current process is mainly initiated by filling out a long PDF application that has many sections and can be overwhelming to fill out. Additionally, all the information from the submitted application is also inputted manually into a spreadsheet, so the possibility of errors are much more frequent, as every piece of information is copied over by hand. 

Our solution that we are working toward aims to eliminate the redundancies in the current process by creating a web application that is simple to fill out and is easy to follow along with. Applicants can create their own accounts, fill out their application with the web-based forms, and can save their progress in the application to come back to it later. It also creates database entries for each user and records their responses in the forms in the database. For the loan processors, different account roles will be created, and roles with admin privileges can look up any applicant by querying their information in the database. 

Finally, a key feature that we have implemented is our emailing system. Once a user creates an account with GEM$, the user will recieve a confirmation email immediately. Moreover, the admin can remind certain users to finish uncompleted applications by the click of a button. We are working on additional features including exporting database entries for each applicant into the original application form for historical documentation purposes. 

We believe that this pushes more accessibility to sustainable energy for the local community in Hawaii, and allows more people to take advantage of going toward the goal of clean energy. By improving the process, we hope that the process is easier and more transparent to those that are 

Some key improvements include:

* User account creation to create new applications and save their application status
* Monitoring of progress of application status to see what stage of processing it is in
* Friendly web-based form for the GEM$ application
* Database querying of loan applicants for loan processors
* User Roles for all parties involved in the application process
* Automation of key processes to ensure that things are handled/addressed in the quickest way possible

Tracking/progress of project issues can be found on our project boards.

<a name="milestone1"></a>
[Milestone 1](https://github.com/orgs/green-loan-portal/projects/1)

<a name="milestone2"></a>
[Milestone 2](https://github.com/orgs/green-loan-portal/projects/2)

<a name="milestone3"></a>
[Milestone 3](https://github.com/orgs/green-loan-portal/projects/3)

<a name="demo"></a>


## User Guide

After accessing our application on the web, you will be greeted by our [homepage](http://simple-green-loans.meteorapp.com):

<img src="images/home.png">

If you don't have an account with us, you can click "Login" on the upper right hand corner of the page, and choose "[Sign up](http://simple-green-loans.meteorapp.com/#/signup)":

<img src="images/register.png">

Once you set up an account, you will receive a confirmation email, and will be taken to this [page](http://simple-green-loans.meteorapp.com/#/Profile):

<img src="images/userlogin.png">

On the user login screen, you can either start/resume your GEM$ application, or you can check the progress of your application to see what stage it is processed at. 

<img src="images/application.png">

The "My Application" link takes you to the loan application that you can fill out, and has sections that you can jump back and forth to. Additionally, you can also save your application to return to it at another time.

<img src="images/profile.png">

When the application is completed, the applicant's status will change, indicating where the application is in the process. 

<img src="images/logout.png">

When the applicant is done with the application, they will get the following notification and will be returned to the home page.

<a name="feedback"></a>
## Community Feedback
Below is feedback on our application we recieved from the local ICS Community:

"The website has a easy but detailed interface. It’s useful that all the information is easy to see and has images, which also helps. Overall, it has a nice layout and gives the information in concise way"

"Seems pretty self explanatory. Looks really easy to use. Really clean cut forms. Signing feature is really fun. Simple, easy, well designed. I like the picture diagram because I learn better with pictures"

"Good logo. Fun scrolling. Good presentation of information. Nice spacing on the forms"

"Nice footer. There should be a start application button instead of view or edit". The red asterisks don't show if we click next "

"Form 2 account field allows letters. Signature gets cleared if we save the forms. You can chose all the check boxes on the authorization form. Authorization form needs to be signed again after we save and finish. There is no "finish" button. The page doesn't redirect after I finish."

"nice footer"

<a name="installation"></a>
## Developer Guide

First, [install Meteor](https://www.meteor.com/install).

Second, [download a copy of green-loan-portal](https://github.com/green-loan-portal/simple-green-loans) by cloning the repository. 

Third, open your terminal and 'cd' into the app directory and install the required libraries with:

```$ meteor npm install```

Once the libraries are installed, you can run the application by invoking:

```$ meteor npm run start```

The first time you run the app, it will create some default users and data. Here is the output:
```
meteor npm run start              

> meteor-application-template-react@ start /home/ryota/GitHub/simple-green-loans/app
> meteor --no-release-check --settings ../config/settings.development.json

[[[[[ ~/GitHub/simple-green-loans/app ]]]]]   

=> Started proxy.                             
=> Started MongoDB.                           
W20191113-21:37:31.866(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
W20191113-21:37:31.929(-10)? (STDERR) While this implementation will work correctly, it is known to be
W20191113-21:37:31.931(-10)? (STDERR) approximately three times slower than the native implementation.
W20191113-21:37:31.932(-10)? (STDERR) In order to use the native implementation instead, run
W20191113-21:37:31.933(-10)? (STDERR) 
W20191113-21:37:31.933(-10)? (STDERR)   meteor npm install --save bcrypt
W20191113-21:37:31.934(-10)? (STDERR) 
W20191113-21:37:31.934(-10)? (STDERR) in the root directory of your application.
I20191113-21:37:32.378(-10)? Creating default data.
=> Started your app.
```

**Note regarding bcrypt warning.** You will also get the following message when you run this application:

```
Note: you are using a pure-JavaScript implementation of bcrypt.
While this implementation will work correctly, it is known to be
approximately three times slower than the native implementation.
In order to use the native implementation instead, run

  meteor npm install --save bcrypt

in the root directory of your application.
```

On some operating systems (particularly Windows), installing bcrypt is much more difficult than implied by the above message. Bcrypt is only used in Meteor for password checking, so the performance implications are negligible until your site has very high traffic. You can safely ignore this warning without any problems during initial stages of development.

If all goes well, the template application will appear at http://localhost:3000. You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/master/config/settings.development.json), or register a new account. Normal users can create their own accounts on the webpage, but if you would like to add administrator/contractor roles, then those would have to be added manually in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/master/config/settings.development.json), with the idea being that site moderators would be the ones responsible for provisioning administrator and contractor accounts for the program.

If you are making changes to database entries, then you may need to reset meteor for the changes to be propagated to the application. Invoke the command```meteor reset``` to reset the database. If done correctly, all the default entries in settings.development.json should be added when ```meteor npm run start``` is executed after resetting. The output should look like: 

```
➜  app git:(master) meteor reset
Project reset.
➜  app git:(master) meteor npm run start

> meteor-application-template-react@ start /Users/ryota/github/ryotabs/simple-green-loans/app
> meteor --no-release-check --settings ../config/settings.development.json

[[[[[ ~/github/ryotabs/simple-green-loans/app ]]]]]

=> Started proxy.
=> Started MongoDB.
W20191204-22:35:30.112(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
W20191204-22:35:30.156(-10)? (STDERR) While this implementation will work correctly, it is known to be
W20191204-22:35:30.156(-10)? (STDERR) approximately three times slower than the native implementation.
W20191204-22:35:30.156(-10)? (STDERR) In order to use the native implementation instead, run
W20191204-22:35:30.156(-10)? (STDERR)
W20191204-22:35:30.157(-10)? (STDERR)   meteor npm install --save bcrypt
W20191204-22:35:30.157(-10)? (STDERR)
W20191204-22:35:30.157(-10)? (STDERR) in the root directory of your application.
I20191204-22:35:30.997(-10)? Creating the default user(s)
I20191204-22:35:30.998(-10)?   Creating user admin@foo.com.
I20191204-22:35:31.231(-10)?   Creating user wileyb@hawaii.edu.
I20191204-22:35:31.447(-10)?   Creating user ryoabs@hawaii.edu.
I20191204-22:35:31.657(-10)?   Creating user default@foo.com.
=> Started your app.

=> App running at: http://localhost:3000/
```



To implement your own changes to the site, you can open the project in your editor/IDE of choice. 

<a name="teammembers"></a>
## Team Members:

[Brody Uehara](https://github.com/brodyu): I primarily worked on front end to enhance user interface with the green loan portal. My goals to this project is to learn more about web development and grow my programming skills. 

[Trey Sumida](https://github.com/trey-sumida): My goal for this project is to learn how to develop an application with a group and code with others. I am looking to improve upon my web development skills. I am more comfortable with front-end UI, and have some experience with databases.

[Arslan Rakhmankulov](https://github.com/arslan-r): My goals for this project is to obtain mastery of the Meteor technology stack. I primarily worked on the back-end along with some front end relating to application forms.

[Ryota Seki](https://github.com/ryotabs): My goals for this project are to get comfortable with using the web application framework Meteor, to learn the different components associated with it (React and Mongo DB), and to learn the process/workflow of working with and contributing to open source projects. I implemented a few features on the front end. 

[Wiley Bui](https://github.com/wileybui): My goals for this project are to work along with others as well as to practice/master the skills that I have learned in this course using JavaScript, React, Meteor, and, especially, MongoDB. I would like to know how the application would come together when it is made and is pushed through production. The skills that I brought to the teams were to add, update, list, and edit the records for the database.
