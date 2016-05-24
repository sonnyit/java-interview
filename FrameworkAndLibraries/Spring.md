Spring
---------------

List questions:

1. [What is Spring?](#)
1. [What is IOC or inversion of control?](#what-is-ioc-or-inversion-of-control-)
1. [What are benefits of Spring Framework?](#)

---
1. ##### What is Spring? [&#10548;](#spring)

1. What are benefits of Spring Framework? [&#10548;](#spring)

1. ##### What is IOC or inversion of control? [&#10548;](#spring)
  By applying DI in your projects, you will find that your code will become significantly simpler, easier to understand, and easier to test.

  With DI, objects are given their dependencies at creation time by some third party that coordinates each object in the system. Objects are not expected to create or obtain their dependencies�dependencies are injected into the objects that need them.

  The key benefit of DI is loose coupling. If an object only knows about its dependencies by their interface (not by their implementation or how they are instantiated), then the dependency can be swapped out with a different implementation without the depending object knowing the difference.

  One of the most common ways that a dependency will be swapped out is with a mock implementation during testing.
