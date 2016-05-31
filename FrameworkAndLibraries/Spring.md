Spring
---------------

List questions:

1. [What is Spring?](#)
1. [What is IOC or inversion of control?](#what-is-ioc-or-inversion-of-control-)
1. [What are benefits of Spring Framework?](#)
1. [Explain the Spring Bean-LifeCycle](#)
1. [What is Bean Factory, have you used XMLBeanFactory?](#)
1. [What are the difference between BeanFactory and ApplicationContext in spring?](#)
1. [What are different modules in spring?](#)
1. [What is the difference between singleton and prototype bean?](#)
1. [What type of transaction Management Spring support?](#)
1. [What is AOP?](#)

---
1. ##### What is Spring? [&#10548;](#spring)

  Spring is an open source development framework for Enterprise Java. The core features of the Spring Framework can be used in developing any Java application, but there are extensions for building web applications on top of the Java EE platform. Spring framework targets to make Java EE development easier to use and promote good programming practice by enabling a POJO-based programming model.

1. ##### What are benefits of Spring Framework? [&#10548;](#spring)

  * **Lightweight:** Spring is lightweight when it comes to size and transparency. The basic version of spring framework is around 2MB.
  * **Inversion of control (IOC):** Loose coupling is achieved in Spring, with the Inversion of Control technique. The objects give their dependencies instead of creating or looking for dependent objects.
  * **Aspect oriented (AOP):** Spring supports Aspect oriented programming and separates application business logic from system services.
  * **Container:** Spring contains and manages the life cycle and configuration of application objects.
  MVC Framework: Spring’s web framework is a well-designed web MVC framework, which provides a great alternative to web frameworks.
  * **Transaction Management:** Spring provides a consistent transaction management interface that can scale down to a local transaction and scale up to global transactions (JTA).
  * **Exception Handling:** Spring provides a convenient API to translate technology-specific exceptions (thrown by JDBC, Hibernate, or JDO) into consistent, unchecked exceptions.

1. ##### What is IOC or inversion of control? [&#10548;](#spring)

  By applying DI in your projects, you will find that your code will become significantly simpler, easier to understand, and easier to test.

  With DI, objects are given their dependencies at creation time by some third party that coordinates each object in the system. Objects are not expected to create or obtain their dependencies dependencies are injected into the objects that need them.

  The key benefit of DI is loose coupling. If an object only knows about its dependencies by their interface (not by their implementation or how they are instantiated), then the dependency can be swapped out with a different implementation without the depending object knowing the difference.

  One of the most common ways that a dependency will be swapped out is with a mock implementation during testing.
  
  [a good explain](http://www.javaworld.com/article/2071914/excellent-explanation-of-dependency-injection--inversion-of-control-.html)

1. ##### Explain the Spring Bean-LifeCycle [&#10548;](#spring)

  Spring framework is based on IOC so we call it as IOC container also So Spring beans reside inside the IOC container. Spring beans are nothing but Plain old java object (POJO).

  Following steps explain their life cycle inside the container.

  1. The container will look the bean definition inside configuration file (e.g. bean.xml).
  2. using reflection container will create the object and if any property is defined inside the bean definition then it will also be set.
  3. If the bean implements the BeanNameAware interface, the factory calls setBeanName() passing the bean’s ID.
  4. If the bean implements the BeanFactoryAware interface, the factory calls setBeanFactory(), passing an instance of itself.
  5. If there are any BeanPostProcessors associated with the bean, their post- ProcessBeforeInitialization() methods will be called before the properties for the Bean are set.
  6. If an init() method is specified for the bean, it will be called.
  7. If the Bean class implements the DisposableBean interface, then the method destroy() will be called when the Application no longer needs the bean reference.
  8. If the Bean definition in the Configuration file contains a 'destroy-method' attribute, then the corresponding method definition in the Bean class will be called.

1. ##### What is Bean Factory, have you used XMLBeanFactory? [&#10548;](#spring)

  BeanFactory is Factory Pattern which is based on IOC design principles.it is used to make a clear separation between application configuration and dependency from actual code. The XmlBeanFactory is one of the implementations of bean Factory which we have used in our project. The org.springframework.beans.factory.xml.XmlBeanFactory is used to create bean instance defined in our XML file.

  ```
  BeanFactory factory = new XmlBeanFactory(new FileInputStream("beans.xml"));
  Or
  ClassPathResource resorce = new ClassPathResource("beans.xml");
  XmlBeanFactory factory = new XmlBeanFactory(resorce);
  ```

1. ##### What are the difference between BeanFactory and ApplicationContext in spring? [&#10548;](#spring)

  This one is very popular spring interview question and often asks in entry level interview.

  ApplicationContext is the preferred way of using spring because of functionality provided by it and interviewer wanted to check whether you are familiar with it or not.

  | ApplicationContext | BeanFactory |
  | ------------------ | ----------- |
  | Here we can have more than one config files possible | In this only one config file or .xml file |
  | Application contexts can publish events to beans that are registered as listeners | Doesn’t support. |
  | Support internationalization (I18N) messages | It’s not |
  | Support application life-cycle events, and validation. | Doesn’t support. |
  | Supports  many enterprise services such JNDI access, EJB integration, remoting | Doesn’t support. |

1. ##### What are different modules in spring? [&#10548;](#spring)

  Spring has seven core modules

  1. The Core container module
  2. Application context module
  3. AOP module (Aspect Oriented Programming)
  4. JDBC abstraction and DAO module
  5. O/R mapping integration module (Object/Relational)
  6. Web module
  7. MVC framework module

1. ##### What is the difference between singleton and prototype bean? [&#10548;](#spring)

1. ##### What type of transaction Management Spring support? [&#10548;](#spring)

  This spring interview questions is little difficult as compared to previous questions just because transaction management is a complex concept and not every developer familiar with it.

  Transaction management is critical in any applications that will interact with the database. The application has to ensure that the data is consistent and the integrity of the data is maintained. Following two type of transaction management is supported by spring:

  1. Programmatic transaction management
  2. Declarative transaction management.

1. ##### What is AOP? [&#10548;](#spring)

  The core construct of AOP is the aspect, which encapsulates behaviors affecting multiple classes into reusable modules.

  AOP is a programming technique that allows a developer to modularize crosscutting concerns,  that cuts across the typical divisions of responsibility, such as logging and transaction management.

  Spring AOP, aspects are implemented using regular classes or regular classes annotated with the @Aspect annotation. You can also check out these Spring MVC interview questions for more focus on Java web development using Spring framework.
