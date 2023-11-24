## Monolithic applications 
If all the functionalities of a project exist in a single codebase, then that application is known as a monolithic application. We all must have designed a monolithic application in our lives in which we were given a problem statement and were asked to design a system with various functionalities. We design our application in various layers like presentation, service, and persistence and then deploy that codebase as a single jar/war file. This is nothing but a monolithic application, where “mono” represents the single codebase containing all the required functionalities. 

<img src="https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/8684ba8d-2595-466a-be15-5399f3f711c1" alt="drawing" width="500" />



But if we were using monolithic applications already, then what led us to microservices? 

- Disadvantages of Monolithic applications:
  ---

1. It becomes too large with time and hence, difficult to manage.
2. We need to redeploy the whole application, even for a small change.
3. As the size of the application increases, its start-up and deployment time also increases.
4. For any new developer joining the project, it is very difficult to understand the logic of a large Monolithic application even if his responsibility is related to a single functionality.
5. Even if a single part of the application is facing a large load/traffic, we need to deploy the instances of the entire application in multiple servers. It is very inefficient and takes up more resources unnecessarily. Hence, horizontal scaling is not feasible in monolithic applications.
6. It is very difficult to adopt any new technology which is well suited for a particular functionality as it affects the entire application, both in terms of time and cost.
7. It is not very reliable, as a single bug in any module can bring down the entire monolithic application.

- Advantages of monolithic applications:
  ---

1. Simple to develop relative to microservices, where skilled developers are required in order to identify and develop the services.
2. Easier to deploy as only a single jar/war file is deployed.
3. Relatively easier and simple to develop in comparison to microservices architecture.
4. The problems of network latency and security are relatively less in comparison to microservices architecture.
5. Developers need not learn different applications, they can keep their focus on one application.


## Microservices 
It is an architectural development style in which the application is made up of smaller services that handle a small portion of the functionality and data by communicating with each other directly using lightweight protocols like HTTP. According to Sam Newman, “Microservices are the small services that work together.” 


<img src="https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/ea97664f-f88b-408d-a8eb-56a98eeaf3fc" alt="drawing" width="500" />





The Microservice architecture has a significant impact on the relationship between the application and the database. Instead of sharing a single database with other microservices, each microservice has its own database. It often results in duplication of some data, but having a database per microservice is essential if you want to benefit from this architecture, as it ensures loose coupling. Another advantage of having a separate database per microservice is that each microservice can use the type of database best suited for its needs. Each service offers a secure module boundary so that different services can be written in different programming languages. There are many patterns involved in microservice architecture like service discovery & registry, caching, API gateway & communication, observability, security, etc.

Principles of microservices:
  ---

- Single responsibility: It is one of the principles defined as a part of the SOLID design pattern. It states that a single unit, either a class, a method, or a microservice should have one and only one responsibility. Each microservice must have a single responsibility and provide a single functionality. You can also say that: the number of microservices you should develop is equal to the number of functionalities you require. The database is also decentralized and, generally, each microservice has its own database.
- Built around business capabilities: In today’s world, where so many technologies exist, there is always a technology that is best suited for implementing a particular functionality. But in monolithic applications, it was a major drawback, as we can’t use different technology for each functionality and hence, need to compromise in particular areas. A microservice shall never restrict itself from adopting an appropriate technology stack or backend database storage that is most suitable for solving the business purpose, i.e., each microservice can use different technology based on business requirements.
- Design for failure: Microservices must be designed with failure cases in mind. Microservices must exploit the advantage of this architecture and going down one microservice should not affect the whole system, other functionalities must remain accessible to the user. But this was not the case in the Monolithic applications, where the failure of one module leads to the downfall of the whole application.




- Advantages of microservices:
  ---

1. It is easy to manage as it is relatively smaller.
2. If there’s any update in one of the microservices, then we need to redeploy only that microservice.
3. Microservices are self-contained and, hence, deployed independently. Their start-up and deployment times are relatively less.
4. It is very easy for a new developer to onboard the project as he needs to understand only a particular microservice providing the functionality he will be working on and not the whole system.
5. If a particular microservice is facing a large load because of the users using that functionality in excess, then we need to scale out that microservice only. Hence, the microservices architecture supports horizontal scaling.
6. Each microservice can use different technology based on the business requirements.
7. If a particular microservice goes down due to some bug, then it doesn’t affect other microservices and the whole system remains intact and continues providing other functionalities to the users.

- Disadvantages of microservices:
  --- 

1. Being a distributed system, it is much more complex than monolithic applications. Its complexity increases with the increase in a number of microservices.
2. Skilled developers are required to work with microservices architecture, which can identify the microservices and manage their inter-communications.
3. Independent deployment of microservices is complicated.
4. Microservices are costly in terms of network usage as they need to interact with each other and all these remote calls result in network latency.
5. Microservices are less secure relative to monolithic applications due to the inter-services communication over the network.
6. Debugging is difficult as the control flows over many microservices and to point out why and where exactly the error occurred is a difficult task.
