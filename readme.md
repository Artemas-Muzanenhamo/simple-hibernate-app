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

## Hibernate Architecture

<p align="center">
    <img src="https://user-images.githubusercontent.com/29547780/34071175-4c1b849c-e26a-11e7-8cc0-a5c5e65d635f.png"></img>
</p>

Our Java application will have a persistent object that lives in both our 
application and also in Hibernate since Hibernate will read our 
objects for mapping the fields in our object to tables in our database.

Hibernate interfaces with the database through JDBC and a `configuration
file` is used to tell Hibernate what JDBC driver to use and what `dialect`
to speak to the SQL database. For example the SQL used to communicate with a 
SQLServer database is different from the SQL used to communicate with 
a MySQL database.

Hibernate also uses JTA and JNDI for communicating with an application
container like JBoss in managing transactions.

So Hibernate works by reading a configuration file which tells it
what database to talk to and how to talk to it and then reading mapping
files that tell it how to map Java objects to relational tables. You write
the Java code that uses the Java API to do things like `save` or `update` your 
data or `query` objects from Hibernate.

<p align="center">
    <img src="https://user-images.githubusercontent.com/29547780/34071283-f2b15948-e26b-11e7-85fe-50c18aa115b4.png"></img>
</p>

Hibernate has a few main types of Classes that you will commonly deal with. 
First we have the `Configuration` Class.

    - Able to read a Hibernate Configuration file and set up Hibernate.
    - We need to create an instance of this class when we first start up
    our application so that we can use Hibernate.
    
Next we have the `SessionFactory` Class.

    - The SessionFactory is able to manage sessions for us.
    - We need to get an instance of the SessionFactory to be able 
    to create a new session.
    - We usually create a single instance of the SessionFactory and hold on 
    to it for the lifetime of our application, then when we want to 
    actually do some work with hibernate, we ask the SessionFactory
    for a session.
    - We could execute hibernate queries directly in a session if 
    we wanted to but it is almost a good idea to ask a session to 
    start a new transaction and then do our work, and when we are done
    `commit` the transaction.
    
So we typically write all our Java code to actually work with the 
`Persistent Object` using the `Hibernate` API in the scope of a 
`Transaction` using a `Session` to interface with Hibernate.

We can also use the `Query` and `Criteria` Classes to query our 
database using a SQL like syntax through the `Query` class, or a more
Object Oriented syntax through the `Criteria` class.