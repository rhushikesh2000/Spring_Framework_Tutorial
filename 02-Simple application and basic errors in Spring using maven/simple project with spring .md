## Spring - Hello World Example

Let us start actual programming with Spring Framework. Before you start writing your first example using Spring framework, you have to make sure that you have set up your Spring environment properly as explained in Spring - Environment Setup Chapter. We also assume that you have a bit of working knowledge on Eclipse IDE.

Now let us proceed to write a simple Spring Application, which will print "Hello World!" or any other message based on the configuration done in Spring Beans Configuration file.

- Step 1 - Create Java Project
  ---
The first step is to create a simple Java Project using Eclipse IDE. Follow the option File → New → Project and finally select Java Project wizard from the wizard list. Now name your project as HelloSpring using the wizard window as follows −



![simple java project](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/1c1da444-a6f4-4eb7-b4e0-fbbdcf250823)


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

As a second step let us add Spring Framework and common logging API libraries in our project. To do this, right-click on your project name HelloSpring and then follow the following option available in the context menu − Build Path → Configure Build Path to display the Java Build Path window as follows −


![java_build_path](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/51715819-c4b4-469c-9e65-34315cd12f55)


Now use Add External JARs button available under the Libraries tab to add the following core JARs from Spring Framework and Common Logging installation directories −

- Step 3 - Create Source Files
  ---
Now let us create actual source files under the HelloSpring project. First we need to create a package called com.firtspring. To do this, right click on src in package explorer section and follow the option − New → Package.

Next we will create HelloWorld.java and MainApp.java files under the com.firtspring package.


![spring_source_files](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/87f5fc1d-deb8-483e-b8a8-665f36d91212)


Here is the content of HelloWorld.java file −
~~~java
package com.firtspring;

public class HelloWorld {
   private String message;

   public void setMessage(String message){
      this.message  = message;
   }
   public void getMessage(){
      System.out.println("Your Message : " + message);
   }
}
~~~
Following is the content of the second file MainApp.java −

~~~java
package com.firtspring;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MainApp {
   public static void main(String[] args) {
      ApplicationContext context = new ClassPathXmlApplicationContext("Beans.xml");
      HelloWorld obj = (HelloWorld) context.getBean("helloWorld");
      obj.getMessage();
   }
}
~~~
- Following two important points are to be noted about the main program −
  ---

The first step is to create an application context where we used framework API ClassPathXmlApplicationContext(). This API loads beans configuration file and eventually based on the provided API, it takes care of creating and initializing all the objects, i.e. beans mentioned in the configuration file.

The second step is used to get the required bean using getBean() method of the created context. This method uses bean ID to return a generic object, which finally can be casted to the actual object. Once you have an object, you can use this object to call any class method.

- Step 4 - Create Bean Configuration File
  ---
You need to create a Bean Configuration file which is an XML file and acts as a cement that glues the beans, i.e. the classes together. This file needs to be created under the src directory.

Usually developers name this file as Beans.xml, but you are independent to choose any name you like. You have to make sure that this file is available in CLASSPATH and use the same name in the main application while creating an application context as shown in MainApp.java file.

The Beans.xml is used to assign unique IDs to different beans and to control the creation of objects with different values without impacting any of the Spring source files. For example, using the following file you can pass any value for "message" variable and you can print different values of message without impacting HelloWorld.java and MainApp.java files. Let us see how it works −
~~~java
<?xml version = "1.0" encoding = "UTF-8"?>

<beans xmlns = "http://www.springframework.org/schema/beans"
   xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation = "http://www.springframework.org/schema/beans
   http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">

   <bean id = "helloWorld" class = "com.firtspring.HelloWorld">
      <property name = "message" value = "Hello World!"/>
   </bean>

</beans>
~~~ 
When Spring application gets loaded into the memory, Framework makes use of the above configuration file to create all the beans defined and assigns them a unique ID as defined in <bean> tag. You can use <property> tag to pass the values of different variables used at the time of object creation.

- Step 5 - Running the Program
  ---
Once you are done with creating the source and beans configuration files, you are ready for this step, which is compiling and running your program. To do this, keep MainApp.Java file tab active and use either Run option available in the Eclipse IDE or use Ctrl + F11 to compile and run your MainApp application. If everything is fine with your application, this will print the following message in Eclipse IDE's console −
~~~java
Your Message : Hello World!
~~~
Congratulations, you have successfully created your first Spring Application. You can see the flexibility of the above Spring application by changing the value of "message" property and keeping both the source files unchanged.



