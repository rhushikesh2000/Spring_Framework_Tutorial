## Spring HelloWorld Example Using Eclipse and Maven

1. Set up a Maven Project
   ---

Create a Maven project by using the Wizard.

![maven project](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/2bce3446-8cdf-49d6-8bd4-d0d286787a68)


click on next ,

![maven 02](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/813392a0-2dae-46a9-bc9f-2e993a5024ab)


Select Maven-quickstart ,

![maven 03](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/38abf0d4-88aa-4f79-aa44-edace058c1bd)


GroupId identifies the project uniquely across all projects, so we need to enforce a naming schema. ArtifactId is the name of the jar without version. and click on finish

![maven 04](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/32a1718c-6c02-4479-9a89-1d015d405d30)

2. Add Spring Dependency
     ---

Edit the pom.xml file and add dependencies of Spring packages. The pom.xml should be changed to:
~~~java
<project xmlns="http://maven.apache.org/POM/4.0.0"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.programcreek.entrylevel</groupId>
  <artifactId>helloworld</artifactId>
  <version>0.0.1-SNAPSHOT</version>
 
	<dependencies>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-core</artifactId>
			<version>${spring.version}</version>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
			<version>${spring.version}</version>
		</dependency>
	</dependencies>
 
	<properties>
		<spring.version>3.2.3.RELEASE</spring.version>
	</properties>
</project>

~~~

3. Create the Spring Bean Configuration File
   ---

Create a bean configuation file named "applicationContext.xml" under src/main/java directory. This xml file specifies the bean you will define in the project. Note the class is the fully qualified class name with the package.
~~~java
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:p="http://www.springframework.org/schema/p"
	xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"
	xmlns:jee="http://www.springframework.org/schema/jee" xmlns:tx="http://www.springframework.org/schema/tx"
	xmlns:task="http://www.springframework.org/schema/task"
	xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/jee http://www.springframework.org/schema/jee/spring-jee-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd http://www.springframework.org/schema/task http://www.springframework.org/schema/task/spring-task-3.2.xsd">
 
	<context:component-scan base-package="com.programcreek.examples" />
 
	<bean id="demo"
		class="com.springcore.Demo">
		<property name="name" value="welcome to Guvi" />
	</bean>
</beans>
~~~

4. Create a Spring Bean
   ---

Create  Bean under /src/main/java directory. The package should be the same with how you declared in the bean configuration file.

~~~java
package com.springcore.demo;
import org.springframework.stereotype.Service;
 
@Service("demo")
public class Demo {
 
	private String name;
 
	public void setName(String name) {
		this.name = name;
	}
 
	public String sayHello() {
		return "Hello! " + name;
	}
}
~~~

5. Run the Maven Project
   ---

Create a Hello class under /src/main/java directory to test the project.
~~~java
package com.springcore.demo;
 
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

 
public class Hello {
 
	@SuppressWarnings("resource")
	public static void main(String[] args) {
 
		// loading the definitions from the given XML file
		ApplicationContext context = new ClassPathXmlApplicationContext(
				"applicationContext.xml");
 
		HelloWorldService service = (HelloWorldService) context
				.getBean("demo");
		String message = service.sayHello();
		System.out.println(message);
 
		//set a new name
		service.setName("Spring");
		message = service.sayHello();
		System.out.println(message);
	}
}
~~~

Right click Hello.java and run it as Java Application. The result is:
~~~java
Hello! Welcome to guvi
Hello! Spring
~~~
