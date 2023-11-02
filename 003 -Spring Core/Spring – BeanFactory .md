## Spring – BeanFactory

The first and foremost thing when we talk about spring is dependency injection which is possible because spring is actually a container and behaves as a factory of Beans. Just like the  BeanFactory interface is the simplest container providing an advanced configuration mechanism to instantiate, configure, and manage the life cycle of beans. Beans are Java objects that are configured at run-time by Spring IoC Container. BeanFactory represents a basic IoC container which is a parent interface of ApplicationContext. BeanFactory uses Beans and their dependencies metadata to create and configure them at run-time. BeanFactory loads the bean definitions and dependency amongst the beans based on a configuration file(XML) or the beans can be directly returned when required using Java Configuration. There are other types of configuration files like LDAP, RDMS, properties files, etc. BeanFactory does not support Annotation-based configuration whereas ApplicationContext does.

![spring container](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/329c9642-7a4a-47b2-9e63-4c23847d7e0a)

Let us do first go through some of the methods of Bean factory before landing up on implementation which are shown below in tabular format below as follows:

| Method                                               | Description                                                                                                                                  |
| ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| containsBean(String name)                            | Does this bean factory contain a bean definition or externally registered singleton instance with the given name?                            |
| getAliases(String name)                              | Return the aliases for the given bean name, if any.                                                                                          |
| getBean(Class<T> requiredType)                       | Return the bean instance that uniquely matches the given object type, if any.                                                                |
| getBean(Class<T> requiredType, Object… args)         | Return an instance, which may be shared or independent, of the specified bean.                                                               |
| getBean(String name)                                 | Return an instance, which may be shared or independent, of the specified bean.                                                               |
| getBean(String name, Class<T> requiredType)          | Return an instance, which may be shared or independent, of the specified bean.                                                               |
| getBean(String name, Object… args)                   | Return an instance, which may be shared or independent, of the specified bean.                                                               |
| getBeanProvider(Class<T> requiredType)               | Return a provider for the specified bean, allowing for lazy on-demand retrieval of instances, including availability and uniqueness options. |
| getBeanProvider(ResolvableType requiredType)         | Return a provider for the specified bean, allowing for lazy on-demand retrieval of instances, including availability and uniqueness options. |
| getType(String name)                                 | Determine the type of the bean with the given name.                                                                                          |
| getType(String name, boolean allowFactoryBeanInit)   | Determine the type of the bean with the given name.                                                                                          |
| isPrototype(String name)                             | Is this bean a prototype? That is, will getBean(java.lang.String) always return independent instances?                                       |
| isSingleton(String name)                             | Is this bean a shared singleton? That is, will getBean(java.lang.String) always return the same instance?                                    |
| isTypeMatch(String name, Class<?> typeToMatch)       | Check whether the bean with the given name matches the specified type.                                                                       |
| isTypeMatch(String name, ResolvableType typeToMatch) | Check whether the bean with the given name matches the specified type. 


- Procedure:
  ---

1. Creating a Spring project using start.spring.io.
2. Creating a POJO class.
3. Configure the Student bean in the bean-factory-demo.xml file.
4. Writing it to application class.
   
- Implementation:
  ---

Step 1: Bean Definition: Create a Student POJO class.

~~~java
// Java Program where we are
// creating a POJO class

// POJO class
public class Student {

  // Member variables
  private String name;
  private String age;

  // Constructor 1
  public Student() {
  }

  // Constructor 2
  public Student(String name, String age) {
    this.name = name;
    this.age = age;
  }

  // Method inside POJO class
  @Override
  public String toString() {

    // Print student class attributes
    return "Student{" + "name='" + name + '\'' + ", age='" + age + '\'' + '}';
  }
}

~~~


Step 2: XML Bean Configuration: Configure the Student bean in the bean-factory-demo.xml file.

~~~java
<?xml version = "1.0" encoding="UTF-8"?>
<beans xmlns = "http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation = "http://www.springframework.org/schema/beans
       https://www.springframework.org/schema/beans/spring-beans.xsd">
            
    <bean id="student" class = "com.gfg.demo.domain.Student">
       <constructor-arg name="name" value="Tina"/>
       <constructor-arg name="age" value="21"/>
    </bean>
</beans>

~~~

Step 3: Main Class

~~~java
// Application class 
@SpringBootApplication

// Main class
public class DemoApplication {

  // Main driver method
  public static void main(String[] args) {

    // Creating object in a spring container (Beans)
    BeanFactory factory = new ClassPathXmlApplicationContext("bean-factory-demo.xml");
    Student student = (Student) factory.getBean("student");

    System.out.println(student);
  }
}
~~~
Output:
~~~java
Student{name='Tina', age='21'}
~~~


Let’s understand the above code with visuals Diagram to understand the flow

![spring cointainer2](https://github.com/rhushikesh2000/Spring_Framework_Tutorial/assets/124034778/c5880fe2-a1e6-4705-b524-94de2f7c46ea)


- The program flow is something like this:
  ---

First of all, the Bean factory reads the XML configuration file and as per the specifications defined in it, it creates the bean of the student POJO.
Then the student reference asks for the student object from the object factory.
Then finally, the spring object factory hands over the spring bean (student) to its reference. Here, note that the bean returned by the object factory is of “Object” type, so we have to typecast it into our desired bean.


