Java Basics 2
---------------

List questions:

1. [What is the right data type to represent a price in Java?](#what-is-the-right-data-type-to-represent-a-price-in-java-)
1. [How do you convert bytes to String?](#how-do-you-convert-bytes-to-string-)
1. [Can we cast an int value into byte variable? what will happen if the value of int is larger than byte?](#can-we-cast-an-int-value-into-byte-variable-what-will-happen-if-the-value-of-int-is-larger-than-byte-)
1. [There are two classes B extends A and C extends B, Can we cast B into C e.g. C = (C) B;]()

---

1. ##### What is the right data type to represent a price in Java? [&#10548;](#java-basics-2)

  BigDecimal if memory is not a concern and Performance is not critical, otherwise double with predefined precision.

1. ##### How do you convert bytes to String? [&#10548;](#java-basics-2)

  You can convert bytes to the string using string constructor which accepts byte[], just make sure that right character encoding otherwise platform's default character encoding will be used which may or may not be same.

1. ##### Can we cast an int value into byte variable? what will happen if the value of int is larger than byte?

  Yes, we can cast but int is 32 bit long in java while byte is 8 bit long in java so when you cast an int to byte higher 24 bits are lost and a byte can only hold a value from -128 to 128.

1. ##### There are two classes B extends A and C extends B, Can we cast B into C e.g. C = (C) B;
