# Hibernate

## What is an ORM

- Object-relational mapping
- technique for converting data between incompatible type systems 
using object-oriented programming languages.
- Translates Objects to tables in our databases automatically so we
can focus on working with objects.

Hibernate is a persistence technology based on the idea of Object-relational
mapping.

<p align="center">
    <img src="https://user-images.githubusercontent.com/29547780/34070958-68a1294a-e266-11e7-93a0-197d38dbf8b1.png"></img>
</p>

## What is Hibernate?

- It's an open source ORM that is able to map Java Objects to most/any
relational database.
- Framework that allows us to specify configuration to use to connect
with our database and to specify the way which our Java objects 
should be mapped to relational tables.
- Creates SQL that is able to perform CRUD operations from the database.
- It presents data from the data as Java objects that we can use and 
manipulate and save back to the database.
- Originally created in 2001 by Gavin King.
- Created to be a better alternative in Java from EJB2.

## Hibernate and JPA

<p align="center">
    <img src="https://user-images.githubusercontent.com/29547780/34071076-84f6adca-e268-11e7-9e18-02e7bc775531.png"></img>
</p>


### JPA

- JPA = Java Persistence API.
- JPA itself is not a framework but a specification that a framework
can implement to be considered JPA compatible.
- You can think of JPA as an Interface and Hibernate as a Class that 
implements that Interface. 

JPA is an abstraction layer over a specific implementation of persistence
in Java. It allows you to write Java code that uses JPA interfaces
which can work with any persistence framework that implements the JPA
spec.

### Hibernate

- Hibernate implements the JPA specification but it also does more
than JPA.