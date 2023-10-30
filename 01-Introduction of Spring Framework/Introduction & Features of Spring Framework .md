## Introduction to Spring Framework
Spring Framework is a method for product development, when the requirement comes with criteria like the need for dependency Injection (DI), lightweight structure for the product, with POJO or plain old java object, AOP or aspect oriented programming, an option for unit testing, modular development options, etc. There are many features in Spring Framework that makes it stand out from other product development framework, such as Spring web services, Spring test content framework, JDBC abstraction layer, Spring MVC framework, a configuration management bundle called IoC container, transaction management, etc.

## What is Spring Framework?
Before the introduction of Enterprise Java Beans (EJB) developers had to use JavaBeans for the creation of web applications. While doing that the developers were not able to provide transaction management and security kind of services through JavaBeans. When EJB was introduced, the problem of developing robust and secure applications was solved but gave rise to another problem of creating home and remote interfaces while developing enterprise applications. Thus, the Spring framework was introduced to ease out the complications related to application development.





## Features of Spring Framework
Now let us look at some features of the Spring Framework that makes it unique and keeps the possibility to ease out the developer’s task.

**1. IoC Container**

---
During runtime, an object needs to be referenced implicitly and the task is taken up by IoC container. This container consists of assembler code that takes care of configuration management. For reference, the packages used are org.springframework.beans and org.springframework.context.

**2. Data Access Framework**

---
This feature enables the developer to use persistence APIs. For storing persistence data in the database using JDBC or Hibernate. Persistence data is that type of data that has its previous version stored even if modified. Way of connection to the database, making sure that the connection is closed, dealing with exceptions, implementation of a transaction management system are some of the other tasks which are under this feature’s umbrella.

**3. Spring MVC Framework**

---
This framework feature helps developers in building web applications on the basis of MVC architecture.

**4. Transaction Management**

---
As the name suggests this framework helps in building a transaction management system without intervening with the code. The Java Transaction API is provided in this framework to the global transaction.

**5. Spring Web Service**

---
   The endpoints of the web services and the definition based on the Java classes are generated and managed using this feature. Managing the endpoints and definition is a complex task and hence the Spring Web service provides a layer-based approach to handle this task.

**6. JDBC Abstraction Layer**

---
This feature helps the developer in handling errors in an easy and efficient manner. The abstraction layer here helps in reducing the JDBC programming code.

**7. Spring TestContext Framework**

---
Last but not least, this feature provides the developer with the unit and integration testing frameworks for Spring applications. Particular and specific integration testing functionalities are also provided as a part of this feature.

The features discussed above in the section provide a list of benefits that are extracted out of the Spring framework and in addition reduces the friction and pain of a developer in repetitive coding and version controls.
