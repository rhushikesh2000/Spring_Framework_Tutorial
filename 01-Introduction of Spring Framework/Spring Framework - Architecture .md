## Spring Framework - Architecture
Spring could potentially be a one-stop shop for all your enterprise applications. However, Spring is modular, allowing you to pick and choose which modules are applicable to you, without having to bring in the rest. The following section provides details about all the modules available in Spring Framework.

The Spring Framework provides about 20 modules which can be used based on an application requirement.


![spring_architecture](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/14f5c8fb-fcfe-4363-a846-c862f4c1b85c)


Spring Framework Architecture
  ---
  
- Core Container
  ---

1. The **Core** Container consists of the Core, Beans, Context, and Expression Language modules the details of which are as follows −

2. The Core module provides the fundamental parts of the framework, including the IoC and Dependency Injection features.

3. The **Bean** module provides BeanFactory, which is a sophisticated implementation of the factory pattern.

4. The **Context** module builds on the solid base provided by the Core and Beans modules and it is a medium to access any objects defined and configured. The ApplicationContext interface is the focal point of the Context module.

5. The **SpEL** module provides a powerful expression language for querying and manipulating an object graph at runtime.



- Data Access/Integration
  ---

1. The Data Access/Integration layer consists of the JDBC, ORM, OXM, JMS and Transaction modules whose detail is as follows −

2. The JDBC module provides a JDBC-abstraction layer that removes the need for tedious JDBC related coding.

3. The ORM module provides integration layers for popular object-relational mapping APIs, including JPA, JDO, Hibernate, and iBatis.

4. The OXM module provides an abstraction layer that supports Object/XML mapping implementations for JAXB, Castor, XMLBeans, JiBX and XStream.

5. The Java Messaging Service JMS module contains features for producing and consuming messages.

6. The Transaction module supports programmatic and declarative transaction management for classes that implement special interfaces and for all your POJOs.

- Web
  ---
1. The Web layer consists of the Web, Web-MVC, Web-Socket, and Web-Portlet modules the details of which are as follows −

2. The Web module provides basic web-oriented integration features such as multipart file-upload functionality and the initialization of the IoC container using servlet listeners and a web-oriented application context.

3. The Web-MVC module contains Spring's Model-View-Controller (MVC) implementation for web applications.

4. The Web-Socket module provides support for WebSocket-based, two-way communication between the client and the server in web applications.

5. The Web-Portlet module provides the MVC implementation to be used in a portlet environment and mirrors the functionality of Web-Servlet module.

- Miscellaneous
  ---
1. There are few other important modules like AOP, Aspects, Instrumentation, Web and Test modules the details of which are as follows −

2. The AOP module provides an aspect-oriented programming implementation allowing you to define method-interceptors and pointcuts to cleanly decouple code that implements functionality that should be separated.

3. The Aspects module provides integration with AspectJ, which is again a powerful and mature AOP framework.

4. The Instrumentation module provides class instrumentation support and class loader implementations to be used in certain application servers.

5. The Messaging module provides support for STOMP as the WebSocket sub-protocol to use in applications. It also supports an annotation programming model for routing and processing STOMP messages from WebSocket clients.

6. The Test module supports the testing of Spring components with JUnit or TestNG frameworks.
