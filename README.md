# SpringMVCCRUDSimple
* CRUD (Create, Read, Update and Delete) application is the most important application for creating any project. It provides an idea to     develop a large project. In spring MVC, we can develop a simple CRUD application.
* CRUD is an acronym for CREATE, READ, UPDATE and DELETE which are basic functions of persistent storage. CRUD operations can use forms or   an interface view to retrieve and return data from a database.

## Choose Correct/Latest Architecture based Web Application Development Approach
There are some approaches given below to apply for Web Application Development

### Using JSP
---------
---Advantages---
1. jsp is java server pages that execute on server. so there is no intimation given to client.
2. jsp separates  presentation logic from its business logic with the help of <jsp:useBean> tag.
3. using jsp we can remove java code from jsp with the help of EL and JSTL totally that make our jsp more secure.
--- Disadvantages---
1. we can develop applications by using jsp but everything is like presentation and business logic in jsp then our 
   jsp becomes heavy weight component we know that a jsp internally converted in servlet so huge amount of java code 
   is placed during jsp translation. so it reduces applications performance.
2. if any application is developed using jsp after some time someone tries to modify its logics that is written in jsp
   who doesn't know much more jsp then he will face problem to modify its logic.
3. JSP pages require more time when  first request is given to the server.

Note: You can get Jsp based web application from here  https://github.com/Er-Adarsh-Chauhan/Jsp-Curd-Operations-Using-useBean-tag

### Using MVC 
---------
--- Advantages---
1. using mvc we can separate presentation , business and its data handling logics through different layers.
2. we don't require to write business logics in jsp here. jsp is used to represent the presentation part only through 
   view of mvc architecture.
3. mvc application is model ,view and controller based architecture to develop web applications so here view for presentation
   part, model for data handling and controller to pass the control between them. 
4. here we can separate business logic from its presentation logic through DAO or ORM supports.  
	
-----Disadvantages-----
1. Increased complexity
2. Need multiple programmers
3. Knowledge on multiple technologies is required.
4. Developer have knowledge of client side code and html code.

## Create Application with CRUD Implementation
In this article we will create applications for personal records management with the following technologies:
* Java Beans and Java Server Pages (JSP)
* JSP Standard Tag Library (JSTL)
* Java Database Connectivity (JDBC)
* Spring Framework version 5.1.8
* Implementation of DAO Design Pattern to get Persistance Data from database 

Note: You can get this web application from here https://github.com/Er-Adarsh-Chauhan/SpringMVCCRUDSimple

The following tools can be used for the development:
* Eclipse IDE for Java EE Developers (one of the newer versions is recommended)
* Apache Tomcat ver 9.0
* Oracle Database 11g

# Using Oracle Database 11g 

## 1. Create Table
`Create table emp99(id number(5),name varchar2(30),salary number(9,2),designation varchar2(30));`

## 2. Create Sequence
A sequence is an object in Oracle SQl that lets you generates unique numbers like table id. so syntax is given below

`create sequence emp99_id`;

## 3. Create Trigger
Trigger is an object of Oracle SQL that runs on a certain Conditions. so syntax is given below

`Create Trigger Emp99_bi`
 ` Before Insert on Emp99`
  `For Each row`
  `Begin `
  	`Select emp99_id_seq.nextval
	Into:new.emp99_id
	from dual;
End;`

`Note : The above steps are to creating table Emp99 and Auto-Update its table id automatically.`
