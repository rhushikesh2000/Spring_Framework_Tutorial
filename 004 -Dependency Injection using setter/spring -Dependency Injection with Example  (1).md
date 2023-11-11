## Spring Dependency Injection with Example

- What is Dependency Injection:
  ---
Dependency Injection is the main functionality provided by Spring IOC(Inversion of Control). The Spring-Core module is responsible for injecting dependencies through either Constructor or Setter methods. The design principle of Inversion of Control emphasizes keeping the Java classes independent of each other and the container frees them from object creation and maintenance. These classes, managed by Spring, must adhere to the standard definition of Java-Bean. Dependency Injection in Spring also ensures loose-coupling between the classes.

- Need for Dependency Injection:
  ---

Suppose class One needs the object of class Two to instantiate or operate a method, then class One is said to be dependent on class Two. Now though it might appear okay to depend a module on the other but, in the real world, this could lead to a lot of problems, including system failure. Hence such dependencies need to be avoided.

Spring IOC resolves such dependencies with Dependency Injection, which makes the code easier to test and reuse. Loose coupling between classes can be possible by defining interfaces for common functionality and the injector will instantiate the objects of required implementation. The task of instantiating objects is done by the container according to the configurations specified by the developer.

- Dependency Lookup
  ---
The Dependency Lookup is an approach where we get the resource after demand. There can be various ways to get the resource for example:

~~~java
A obj = new AImpl();
~~~

In such way, we get the resource(instance of A class) directly by new keyword. Another way is factory method:
~~~java
A obj = A.getA();
~~~

This way, we get the resource (instance of A class) by calling the static factory method getA().

Alternatively, we can get the resource by JNDI (Java Naming Directory Interface) as:

~~~java
Context ctx = new InitialContext();  
Context environmentCtx = (Context) ctx.lookup("java:comp/env");  
A obj = (A)environmentCtx.lookup("A");
~~~
There can be various ways to get the resource to obtain the resource. Let's see the problem in this approach.


- Problems of Dependency Lookup :
  ---
There are mainly two problems of dependency lookup.

- tight coupling The dependency lookup approach makes the code tightly coupled. If resource is changed, we need to perform a lot of modification in the code.
- Not easy for testing This approach creates a lot of problems while testing the application especially in black box testing.


- Dependency Injection
  ---
The Dependency Injection is a design pattern that removes the dependency of the programs. In such case we provide the information from the external source such as XML file. It makes our code loosely coupled and easier for testing. In such case we write the code as:
~~~java
class Employee{  
Address address;  
  
Employee(Address address){  
this.address=address;  
}  
public void setAddress(Address address){  
this.address=address;  
}  
  
}

~~~

In such case, instance of Address class is provided by external souce such as XML file either by constructor or setter method.

- Two ways to perform Dependency Injection in Spring framework
  ---

- By Constructor
- By Setter method


