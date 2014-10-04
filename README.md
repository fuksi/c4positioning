
####PLEASE ONLY CREATE PULL REQUEST FOR FILES INSIDE MAINPROJECT, README FILE IS MAINTAINED SEPARATELY

**DEADLINE 4th of October 23:59 (Friday)**
Return Github project linkto Tuubi.

*Topics* 

Data analysis and visualization of user movements in the school areas, in order to provides different information for related parties with certain purposes such as: For student to check if labs have enough spaces, to check information about the cafeteria, and for example for the cafeteria as well to coordinate resources for busy time. 

1) navigation service
2) community service (friends)
3) data analysis and visualization of the user movements (=big brother is watching you)
4) teaching (e-learning): how to utilize the system in the classroom?
5) a mobile game based on indoor positioning system

Questions for describing the system:

In which ways it is possible to argue and to state that you are really developing state-of-the-art solution?
How is it possible to convince and motivate your customer with the documentation?
Which parts/functionalities of the product should be mandatory and which not? Why?
How you will state you are really building a quality product?
How you will guarantee your process and team quality?
How you are able to get enough money from the customer? How much money is needed, what is enough? How to decrease the costs?
What are the main risks in your upcoming project? How would you document the risks and the solutions?



*Document structure*

###1. Cover

Title: Software Requirement Specs of iCheck position system. 
Team name: AFB (Apple Fan Boys)
Team members: Tran Dinh Thien Phuc, Tran Bao, Nguyen Thu Ha Phuong
Date: 18 Sep 2014

###2. Introduction

Long queue at the cafeteria, no empty space in lab, free workspace is unexpectly occuppied and so on. These issues have being going on at Metropolia for a long time, and now we've came with a solution. iCheck is a service, which informs users, and allow users to research quickly the situation at different desired locations. The system behind iCheck provides functionalities such as remotely review the current queue of the cafeteria, check available lab rooms, look for closest avaialble toilet, check to see if a lecturer is avaialble. More over, we connect you with all platforms that available is the school system, such as Tuubi, Lukkarit, Moodle, etc, in order to privide appropriate recommondation, for a more efficient day at Metropolia. iCheck is not only for students, different parties at Metropolia can utilize iCheck to alternate classrooms, human resources, reception schedule and so on. 

iCheck implements new system architecture to address already existing and challenging issues. The services provide by the system can be deployed into all platforms with seamless experience through the modern application of PhoneGap. iCheck system center, implementing Orcale database, powerred with Apache, will be place in school local servers, in order to create a lighting speed user experience. 

###3. Use cases

* Users groups, brief and definition:  
 * User/Visitor: not registered user, has never used the service before. The visitor the can review the service or register as a user/client or a user/service provider
 * User/Client: registered user, has all the rights as visitors, plus user can use the services offered by the system.
 * User/Service Provider: registered user, has all the rights as visitors, client, plus the ability to propose and offer services
 * Admin: system administrator, has all rights in the system, can access and manage clients and services providers' attributes. 

* Use case diagrams

![Use case diagrams](http://users.metropolia.fi/~dinht/UseCaseC4.jpg)
http://users.metropolia.fi/~dinht/UseCaseC4.jpg

* Use case scenarios (based on template)

#####Example 1: A register user wants to locate closest free labrooms.  

1. initial state  
 * Sitting in front of a working PC or other similar devices
2. normal flow
 * User clicks on iCheck app on the phone (or open iCheck.io on web browsers)
 * Locate login button on top right and click on it
 * Input login details and clicks login
 * At user interface, clicks on school services in 'Service' tab
 * In school services - click on 'Locate free lab rooms'
 * Cick on one of the listed lab rooms for direction if needed
 * (Follow direction)
3. what can go wrong  
 * Device's internet connection is not working
 * Mistyped login credentials
 * Service unavailable at the moment
 * Device's location serviced is turn off
4. other activites going on at the same time  
 * User multitasks at the same time on phone i.e. messaging, playgame while waiting for the app to load
 * User left the app window for more than limited time to do other stuffs, app session then is stopped.
5. Successful - end state
 * Free closest lab rooms are listed on screen  

#####Example 2: Cafeteria wants to notice or students and staffs about change in lunch schedule tomorrow.  

1. initial state  
  * Sitting in front of a working PC or other similar devices
2. normal flow  
  * user clicks on iCheck app for Enterprise on the phone (or open iCheckE.io on web browsers)
  * Locate login button on top right and click on it
  * Input login credentials and clicks login
  * At UI for Enterprise, locate 'Quick notice' in the bottom and click on it
  * In 'Target Group' section, locate and click on 'Students' and 'Staffs'
  * In 'Content' section, enter text about the change in schedule
  * When done, click send
3. What can go wrong  
  * Receivers notification setting is off
  * Mistyped login credentials
  * Internet connection lost in the middle of process transaction  
4. Other activites going on at the same time  
  * User multitasks at the same time on phone i.e. messaging, playgame while waiting for the app to load
  * User left the app window for more than limited time to do other stuffs, app session then is stopped.  
5. Successful - end state
  * All target groups' users received the notifications   


###4. System architecture

__*High-level overview of the system*__
iCheck is a application, which using indoor system positioning to check availability of lab or study room,toilet and University's cafeteria.  

__*Main modules and their functions represented*__

![System architecture](http://users.metropolia.fi/~dinht/Architecture.jpg)  

* UserVisitor class is a class contains fields about the current which is not login yet. A session when visitor visit the front page of the app will trigger a instantiation of this class, of which methods provides for example form to register, confirmation if the visitor can use the service, which is intended for Metropolia students, staffs, and service providers.  
* UserClient class is a class for users such as students and staffs. UserSvProvider is a class for service providers. Passsed the registration process, these users have already have the app installed on a client. A connection to app should trigger a instantiation of the class, along with a session of the services. The same apply for class Admins  
* __*UserSessions*__ is a main class for every session created by a user or an admin. An object of UserSessions should contains information i. e. about what kind of session this is, from a admin, students or service provider? When the session started? What type of device the client is using? and so on. The relationship between database and UserSessions is fundamental to the input, output of every sessions.  
* As mentioned MySQLDatabase contains information about users, admins, and services as well as everything captured in the sessions in the table i. e. userLog, userLocation, serviceInit, sessionLength and so on, in order for system development later on in the project. 


###5. Requirements (in traceable (and measurable) format)

#####1. Functional requirements:

 * Account: If the visitors are not logged in, application should have the options for them to choose: log in if they have account or sign up if they have not got the account yet. 
 * Forget Password: If users forget their password, application can ask the user to provide their registered email address in order to send them their forgotten password.
 * If users login process success, the application should show the features list like getcheckAttendance, show cafeteria condition, show free labs , show available WC.
 * Users have to post their current postion to the application in order to get the Check Attendence functions, get currently available WC.
 * Users can access all the information of themself
 * Users can give feedback or report bugs through feedback form and admins receive the feedback

#####2. Non-functional system requirements  

 * Usability: System should be simple, clear, and easy for user to interact with. Front page will contain the login and sign up features, each features will have its form for user to process. After users have logged in, system will show a list of features. Some features will need the position of users, so system will ask them to access their postion information. Each features will have its page, which simply show the information in that features.  

 * Reliability: how do you ensure that your system is reliable? List the possible system failures and how the system reacts to them. System has to protect user's information. Only admins and service provider can view part of user's information which is needed for their tasks. The user's position information should be also secured so that other cannot view it. For some tasks, users have to provide their position so that they cannot cheat like in check Attendance features.
Possible system failure may occur:   
  * Uncorrected ID/password -> log in again/forgot password/register
  * Cannot access position -> post Position/check phone connectivity/cancel
   
 * Efficiency: Since there thousands of people using the service, the system requires using some metrics which can help the system guarantee the speed, accessibility of the service. Fortunately, most uses occurs when users are at the university using the university's network, then the other important thing we need to consider is a user's ability to quickly get to know the application of the service. 

Along with the review of the service for guests, when login for the first time, users can go through simple hints how to quickly accomplish tasks with the user interfaces. These hint are spreads into different level, so it would not make users feel frustrated by going all the hints at one time.


What other non-functional requirements should be documented?
* Flexibility: Other extra or improvement should be discussed and planned from the beginning in order to make decision during the development process
* Portability: Application can run smoothly in mutiple platforms.
* Accessibility: Application should be easily accessed and used by everyone. Users do not have troubles to access and use the application.
* Scalability: System has the capability to grow in its capacity to meet the rising demand for its services offered.

###6. User interface

Views and components are listed and described by words

Views

	* Start page
	* Login
	* Sign up
	* Main page( with features list)
	* Check Attendance
	* Cafeteria condition
	* Available labs room
	* Available nearest WC
	
Components

	* Banner
	* Navigation
	* Show list button
	* Back button
	* Footer
	
Components

	* Banner: in the top middle of the page, it is displayed in every pages.
	* Navigation: in the start page, the navigation will contain login and logout, change language categories
	* Show list button: it display in everypage except the start page. It is located in the top right corner of the page. It shows the langguage settings and logout. 
	* Back button: User can go to the previous page by the back button. This button is located in the top left of the page.
	* Footer: contain information like about author, service, legal issues.
	
Pages

	* Start page: select language, description of the app in the middle, Login and Logout selection link. Actually users can login and logout from the main page.
	* Login: Username, password, submit, sign up link
	* Sign up: Form(email,username,password), agree to the Terms & Conditions, fill in the form , create new account and finally submit.
	* Main page: a list of main function features(check attendance, cafeteria condition, available labs room, available nearest WC)
	* Check attendance: require users to post their position. Display the class and subjects, then users can check Check Attendance button to confirm. If system cannot get user's position, a message will display to announce to users that they have to check the phone connectivity. If users are not in the class, systems announce to user that it cannot complete the action, please check again.
	* Cafeteria condition: Display the condition of cafeteria at the moment. This features side can display such as(crowded, normal, solitary) and also display the food that are served in that cafeteria, also the opened and closed time.
	* Available labs room: Users can simply press the Available labs room button then the page displays which room is available, number of available of seats and number of available computer, time of next class in that room.
	* Avalable nearest WC: require users to post their position. Simply show the map and get a guide line for users to go to their nearest WC.
	


####7. Project management, self reflection

 * Working hours for this documentation was around a day or half a day for whole team.
Hours separately per person: Phuc 6 hours,Bao 6 hours.  

 * It was difficult to estimate the workload since we have to decided the limit of the project any time since we are doing only the documentation, not the implementation of the project. Real working hours was quite a bit less than estimated the the start of 2nd year probably is busiest time of the whole degree. The product is relevant, so yes, as a stakeholder, I would buy the product. The most difficult part of the documentation is trying the list the specification of a product that you not really going to make. Then we who are making this documentation are not the stakeholder of the documentation itself, then we find it hard to get the motivation to think deeper and develop the project as well as the documentation. 

