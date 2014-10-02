//This is a comment by Tran Dinh Thien Phuc (1305011)
//Luu Tuan Dung (1305915)
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
Team members: Tran Dinh Thien Phuc, Luu Tuan Dung
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

* Use case scenarios (based on template)
* Depiction of one use case as a flow chart

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

Functional requirements: *Consider the privacy of users*
Non-functional system requirements
Usability: how do you ensure that your system is easy to use?
Reliability: how do you ensure that your system is reliable? List the possible system failures and how the system reacts to them
Efficiency: there are multiple people using your system. How do ensure that the system is efficient enough? What metrics would you use?
What other non-functional requirements should be documented?
What kind of metrics you should use to guarantee unambiguity?

###6. User interface

What are the views / components of the system? What are the functionalities of each view?
Illustrate each view and what it is used for (Textual explanation ok, no need for pictures!)

7. Project management, self reflection

List the realized working hours, that is, how many hours did this work really take. List the hours separately per person.
Was it difficult to estimate workload, how much the estimation differed from real working hours?
What would you do differently on the next project? Was your project success, would you buy your product?
What was the most difficult part in the documentation? Is there something that you were not satisfied with?  
  

Grading

Max points: 30 p.

+6: cover+ introduction + project management (1,2,7)
+6: use cases (3)
+6: system overview (4)
+6: requirements (5)
+6: user interface (6)

