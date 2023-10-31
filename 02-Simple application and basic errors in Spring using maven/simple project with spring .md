## Spring - Hello World Example

Let us start actual programming with Spring Framework. Before you start writing your first example using Spring framework, you have to make sure that you have set up your Spring environment properly as explained in Spring - Environment Setup Chapter. We also assume that you have a bit of working knowledge on Eclipse IDE.

Now let us proceed to write a simple Spring Application, which will print "Hello World!" or any other message based on the configuration done in Spring Beans Configuration file.

- Step 1 - Create Java Project
  ---
The first step is to create a simple Java Project using Eclipse IDE. Follow the option File → New → Project and finally select Java Project wizard from the wizard list. Now name your project as HelloSpring using the wizard window as follows −

![hello_spring_wizard](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/15da96de-a842-418e-8251-c67a3bb42616)

Once your project is created successfully, you will have the following content in your Project Explorer −

- Step 2 -  Add spring jar files
  ---
There are mainly three jar files required to run this application.

- org.springframework.core-3.0.1.RELEASE-A
- com.springsource.org.apache.commons.logging-1.1.1
- org.springframework.beans-3.0.1.RELEASE-A
  
For the future use, You can download the required jar files for spring core application.

[**download the core jar files for spring**](https://static.javatpoint.com/src/sp/spcorejars.zip)


[**download the all jar files for spring including aop, mvc, j2ee, remoting, oxm, etc.**](https://static.javatpoint.com/src/sp/springjars.zip)



To run this example, you need to load only spring core jar files.

To load the jar files in eclipse IDE, Right click on your project - Build Path - Add external Jars - select all the required jar files - finish..
