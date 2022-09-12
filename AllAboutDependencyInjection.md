## What is Inversion Of Control (IoC) ?
Inversion Of Control (IoC) is a concept of software engineering, where the control of objects or a block of a program is transferred to a container or framework. IoC allows a container to take control of the flow of a program and make calls to our custom code rather than making calls to a library. To implement IoC, the Dependency Injection concept is used.

## What is Spring Container ?
In the Spring framework, the interface ‘ApplicationContext’ represents the Spring container. The Spring container takes responsibility of instantiating, configuring and assembling objects (Spring beans), and managing their life cycles as well. In order to create beans, the Spring container takes help of configuration metadata, which can be in the form of either XML configuration or annotations. Spring Container is the short form of  ‘Spring IoC container’ and they are used interchangeably. For further reading on Spring Container, kindly visit Spring Official website (spring.io).

## What is a Spring Bean ?
In the context of Spring Framework, an object which is managed (instantiated, configured & assembled) by the Spring container is known as Spring bean.

## What is Dependency in Spring ?
Let’s consider a simple core Java class ‘Invoice’ as shown below.
<pre>
public class Invoice {
   String name;
   Double amount;
   List<String> items;
   Vendor vendor;
   TaxDetails taxDetails;
}

class Vendor {}

interface TaxDetails {}
</pre>

As shown in the code snippet above, Invoice is a class which has various instance variables: name, amount, items, vendor, and taxDetails. If we want to create an object of Invoice, we need all instance variables. In other words, instantiation of class Invoice depends on all the instance variables inside the class. In the context of Spring, our Invoice class is a bean and it has six dependencies: name, amount, items, vendor, and taxDetails. Now, let’s talk about different types of dependencies.

Based on the data type of the instance variable, we have three types of dependencies.

## Which type of dependencies can a Spring Container Inject ?
1) Primitive Type  
2) Collection Type  
3) Reference Type (User defined Type)

### Primitive Type Dependency 
If a variable has its data type from the below list, then the dependency is Primitive Type Dependency. Please note that String is also considered as a primitive type in Spring.

byte, short, int, long, float, double, boolean, char, String

### Collection Type Dependency 
If a variable has its data type from the below list, then the dependency is Collection Type Dependency. Please note that the Properties is a class, whereas all others are interface. They come under java.util package.
List, Set, Map, Properties

### Reference Type Dependency
If a variable is created using a class or an interface as its data type, then the dependency is Reference Type Dependency. In real time Reference Type Dependency is the most commonly used term for dependency. In our example above, variables vendor and taxDetails come under this dependency.

## What is an Object Dependency ?
When an object depends on another object(s), we call it object dependency. In fact, this is same as Reference Type Dependency as described above. In the context of Spring framework, when a bean depends on another bean(s), we also call it bean dependency. Moreover, the parent bean is called the dependent bean and the instance variables inside the bean are called dependencies.

## What is Injection in the term Dependency Injection ?
As the word ‘injection’ suggests, inserting something into another thing. In fact, injection is the process of inserting values to variables while creating an object. If we talk about objects, the process of inserting one object into another object is called injection. In this case variable will be a reference type variable.

## What is Spring Dependency Injection (DI) ?
Dependency Injection (DI) is the feature of the core module of the Spring Framework, where the Spring Container injects other objects into an object. Here, other objects are nothing but dependencies (instance variables) which are declared in the class (Spring Bean).

## How many ways to implement Dependency Injection ?
There are two ways to implement dependency injection:
1) XML Based
2) Java Annotation Based

## What is Autowiring ?
Spring Container detects the relationship between the beans either by reading the XML Configuration file or by scanning the Java annotations at the time of booting up the application. Further, it will create the objects & wire the dependencies. Since Spring Container does this process automatically, it is referred to as Autowiring i.e., Automatic Wiring. Developer only needs to provide @Autowired annotation at a specific place.

## Autowire Disambiguation
If more than one bean of the same type is available in the container, the framework will throw a NoUniqueBeanDefinitionException, indicating that more than one bean is available for autowiring. This is referred to as autowire Disambiguation. To resolve this conflict, we need to tell Spring explicitly which bean we want to inject. In order to handle this situation, we make use of @Primary or @Qualifier annotations along with @Autowired annotation. The complete detail is provided in a separate article on How to use @Qualifier and @Primary Annotations?.

We can use autowiring on properties, setters, and constructors. Hence, there are three types of dependency injection.

## What are the types of Dependency Injection ?
Setter Based Injection
When Spring Container provides values to variables using setter method, we call it Setter Injection. In this case, Spring Container uses the default constructor to create the object. When the annotation @Autowired is used on top of the class’s setter method, it is known as Setter based Dependency Injection.
<pre>
@Component 
public class Vendor{
   int code; 
   String name;
} 

public class Invoice{
   
   private Vendor vendor;

   @Autowired
   public void setVendor(Vendor vendor){
      this.vendor=vendor;
   }
}
</pre> 
As shown in the example above, Vendor class has been created using @Component annotation. Hence, Spring container will automatically detect it while starting up the application and will create a bean object for Vendor class. Further, when Spring container detects that the Vendor bean object has been Autowired (using @Autowired) into Invoice class setVendor() method, the bean object created for Vendor will be injected into Invoice class via setter method.

## Constructor Based Injection
When Spring Container provides values to variables using parameterized constructor, we call it Constructor Injection. Please note that Spring Container uses parameterized constructor to create the object in this case. When the annotation @Autowired is used on top of the class constructor, it is known as Constructor-based Dependency Injection.

<pre>
@Component 
public class Vendor{  
   int code;   
   String name;
} 

public class Invoice{

   private Vendor vendor;

   @Autowired
   public Invoice(Vendor vendor){
      this.vendor=vendor;
   } 
}
</pre>
As shown in the example above, Vendor class has been created using @Component annotation. Hence, Spring container will automatically detect it while starting up the application and will create a bean object for Vendor class. Further, when Spring container detects that the Vendor bean object has been Autowired (using @Autowired) into Invoice class constructor, the bean object created for Vendor will be injected into Invoice class via constructor.

## Field or Property Based Injection 
When the annotation @Autowired is used on top of the field or property in the class, it is known as Field-based Dependency Injection.

<pre>
@Component 
public class Vendor{  
   int code;   
   String name;
} 

public class Invoice{

  @Autowired
  private Vendor vendor;
}
</pre>
Similar to above both Dependency Injection, here the Autowiring takes place by means of the field ‘vendor’. The bean object created for Vendor class will be Autowired & injected via the field, ‘vendor’ in Invoice class.

In this case, while creating the Invoice object, if there’s no constructor or setter method is available to inject the Vendor bean, the container will use reflection to inject Vendor into Invoice.

## When to use @Autowired(required = false) ?
Suppose a bean is not registered with Spring Container and we try to apply the @Autowired annotation on it, then Spring will throw an exception because the required dependency is missing. In this case, we can use @Autowired(required = false) to tell Spring Container that this dependency is optional. On doing so, Spring will not throw any exception of the missing dependency.

## How to inject Java Collections as a Dependency in Spring ?
As aforementioned, we can use List, Set, Map and Properties as an example of the dependency injection.

Let’s create an example bean class:
<pre>
public class ListCollectionBean { 

   @Autowired 
   private List<String> listOfLanguages; 
   public void printLanguageList() {
       System.out.println(listOfLanguages); 
   } 
}
</pre>
Now, let’s register the ListCollectionBean in the configuration setup class:

<pre>
@Configuration 
public class ListCollectionConfig { 
   
   @Bean 
   public ListCollectionBean getListCollectionBean() {
      return new ListCollectionBean(); 
   }
   
   @Bean 
   public List<String> listOfLanguages() {
      return List.of("Java", "Scala", "Python"); 
   } 
}
</pre>
Similarly, we can inject any type of Collection as a dependency.

## How to inject bean/object references as an element of a Collection in Spring ?
In the above example, we have seen the injection of a Collection where elements are String. Here in this section we will look at a collection where elements of the collection will be bean/object references.

Let’s create a bean:
<pre>
public class MyTestBean { 

    private String name; 
 
    public MyTestBean(String Name){
       this.name=name;
    } 
}
</pre>
And add a List of MyTestBean as a property to the MyCollectionBean class as below:
<pre>
public class MyCollectionBean {
   
   @Autowired(required = false) 
   private List<MyTestBean> beanList; 
   
   public void printBeanList() { 
      System.out.println(beanList); 
   } 
}
</pre>
Now, let’s create a configuration class and create some beans of type MyTestBean as below:
<pre>
@Configuration 
public class CollectionConfig { 
   
   @Bean 
   public MyTestBean getFirstObject() {
      return new MyTestBean("bean1"); 
   } 
   
   @Bean 
   public MyTestBean getSecondObject() {
      return new MyTestBean("bean2"); 
   } 
  
   @Bean 
   public MyTestBean getThirdObject() {
      return new MyTestBean("bean3"); 
   } 
   // other methods 
}
</pre>

Here, Spring Container will inject the specific beans of the MyTestBean type into the collection. Further, on invoking the printBeanList() method, the output will show the bean names as list elements: [bean1, bean2, bean3].

If you want Spring container to inject the beans in a particular order, you can use @Order annotation with index. For example, below code demonstrates the concept. In order to have complete understanding of @Order annotation, kindly visit a separate article on the @Order annotation of Spring Annotations.

<pre>
@Configuration 
public class CollectionConfig { 
 
   @Bean 
   @Order(1)
   public MyTestBean getFirstObject() {
      return new MyTestBean("bean1"); 
   } 
 
   @Bean 
   @Order(0)
   public MyTestBean getSecondObject() {
      return new MyTestBean("bean2"); 
   } 
 
   @Bean  
   @Order(2)  
   public MyTestBean getThirdObject() {
      return new MyTestBean("bean3"); 
   } 
}
</pre>
As per the @Order annotation shown above, the injection order will be: bean2, bean1, bean3

## What are the benefits of Dependency Injection ?
1) Most importantly, the dependency Injection helps in achieving loose coupling between objects.

2) As the dependency between objects becomes loosely coupled, it helps the developers to test the module by injecting the dependent Mock Objects (for example, making use of Spring Mockito).

3) When the objects are independent of each other & can be injected, the scope of code reusability increases.

4) It makes code more readable. We don’t have to look through all the code to see what dependencies we need to satisfy for a given component. They are all visible in the interface.

## What are the disadvantages of Dependency Injection ?
1) As the Dependency Injection offers loose coupling, it concludes increasing the number of classes & interfaces.

2) While implementing the Dependency Injection, Spring container takes the control rather than the developer. Hence, it becomes difficult for the developers to learn how things work in the background & also to have customization.

Reference [javatechonline.com](https://javatechonline.com/spring-dependency-injection/)