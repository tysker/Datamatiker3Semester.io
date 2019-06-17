[**HOME**](../index.md)

# Java Persistance Aplication And Object Relational Mapping

___

**Questions**

* **Explain the rationale behind the topic Object Relational Mapping and the Pros and Cons in using ORM**

     * Tecnique for converting data between  tables in relational databases to objects in an object oriented language and vice versa.
     * Creates in effect a "virtual" object database.
       
 * **Pros**
     * ORM typically reduces the amount of code that needs to be written.
     * Avoids low level JDBC and SQL code.
     * Provides database and schema independence.
     * It allows us to use the OO-paradgrim.
     * Often protects against SQL Injection, but still: always validate inputs.
         
 * **Cons**
      * The high level of abstraction can obscure what is actually happening in the implementation code. 
      * Be aware of JPA’s Convention-Over-Configuration Strategy.
      * Heavy reliance on ORM software has been cited as a major factor in producing poorly designed databases.

* **Explain the JPA strategy for handling Object Relational Mapping and important classes/annotations involved.**
The strategy is to automate the mapping of objects into or from relational database tables . Each object relates to a tuple of a table. (tuble: linje i Databasen). 
    Some important classes/annotations:
            i. @Entity - makes a class an entity class that will be persisted in a corresponding database    table.
            ii. @Transient - a transient property of an entity class will not be mapped to the database.
            iii. @OneToMany - annotates a relationship with a different entity.
            iv. @ManyToMany - another relationship resulting in an intermediate table, aka lookup table.


* **Outline some of the fundamental differences in Database handling using plain JDBC versus JPA.**

     * JDBC is a standard for Database Access
     * JPA is a standard for ORM
       
     **JDBC** is a standard for connecting to a DB directly and running SQL against it - e.g SELECT * FROM USERS, etc. Data sets can be      returned which you can handle in your app, and you can do all the usual things like INSERT, DELETE, run stored procedures, etc.          It is one of the underlying technologies behind most Java database access (including JPA providers).

     One of the issues with traditional JDBC apps is that you can often have some crappy code where lots of mapping between data sets        and objects occur, logic is mixed in with SQL, etc.

     **JPA** is a standard for Object Relational Mapping. This is a technology which allows you to map between objects in code and            database tables. This can "hide" the SQL from the developer so that all they deal with are Java classes, and the provider allows        you to save them and load them magically. Mostly, XML mapping files or annotations on getters and setters can be used to tell the        JPA provider which fields on your object map to which fields in the DB

* **Explain some of the problems which occur when you write tests that involves database operations.**


* **Explain ways (one strategy is enough) to mock away the database when writing unit tests.**


* **Explain ways to run integration tests on Travis using a “real” MySQL server.**

___


**Slides**

 * [**Object Relationel Mapping**](../files/ORM-intro.pdf)
       
___


**gitignore**

* /src/main/resources/META-INF/persistence.xml

____


**Create New Project**

* [**New Project**](ormjpa.md)

____


**Cheat sheet**

* <a href="https://docs.google.com/document/d/1C3BNKSonlCVUhdRyXkHS5Spp1hIKMRgxuqAD9lh0ak0/edit?usp=sharing" target="_blank">**Implementing Relations Cheatsheet**</a>

____


**Importen Links**

* <a href="https://en.wikibooks.org/wiki/Java_Persistence/JPQL" target="_blank">**JPAQL Queries**</a>
* <a href="https://en.wikibooks.org/wiki/Java_Persistence" target="_blank">**Java Persistence**</a>
* <a href="https://www.objectdb.com/api/java/jpa/annotations" target="_blank">**List of ALL JPA-annotations**</a>
* <a href="https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html" target="_blank">**EntityManager - Method Summary**</a>
 * <a href="https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html#persist(java.lang.Object)" target="_blank">**Persist-Merge-Remove-Find**</a>
 * <a href="https://github.com/tysker/Datamatiker3Semester.io/blob/master/JPA_TEST_AndMockingWithMaven.pdf">**How to create a embeded Test**</a>
 * <a href="https://www.javatpoint.com/jpa-cascading-operations" target="_blank">**JPA Cascading Operations**</a>
 * <a href="https://www.javatpoint.com/jpa-tutorial" target="_blank">**JPA Tutorial**</a>
 * <a href="https://www.tutorialspoint.com/jpa/" target="_blank">**JPA Tutorial Points**</a>
 
 ____

 **Requirements for Entity Classes**
* The class must be annotated with the @Entity annotation.
* The class must have (at least) a public or protected, no-argument constructor. 
* The class must not be declared final. No methods or persistent instance variables must be declared final.
* If an entity instance is passed by value as a detached object, the class must implement the Serializable interface.
* Entities may extend both entity and non-entity classes, and non-entity classes may extend entity classes.
* Persistent instance variables must be declared private, protected, or package-private and can be accessed directly only by the entity class's methods. Clients must access the entity's state through accessor or business methods.

____

**Notes**

* We only use annotation based mappings.
* The Java Persistence API (JPA) is a Java specification for accessing, persisting, and managing data between Java objects / classes and a relational database.
* You must put the annotation on the get method, not the set method. 
* The **EntityManager.remove()** operation is used to delete an object from the database. remove does not directly delete the object from the database, it marks the object to be deleted in the persistence context (transaction). When the transaction is committed, or if the persistence context is flushed, then the object will be deleted from the database.
* **NEVER** commit your persistence.xml file. Add persistence.xml to your .gitignore file

____

**Mapping**

* The first thing that you need to do to persist something in Java is define how it is to be persisted. This is called the mapping process 

____

**Persisting**

* The EntityManager represents the application session or dialog with the database.
* The EntityManager provides an API for all required persistence operations. These include the following CRUD operations:
  1. persist (INSERT)
  2. merge (UPDATE)
  3. remove (DELETE)
  4. find (SELECT)
* The EntityManager is an object-oriented API, so does not map directly onto database SQL or DML operations. For example to update an object, you just need to read the object and change its state through its set methods, and then call commit on the transaction. The EntityManager figures out which objects you changed and performs the correct updates to the database, there is no explicit update operation in JPA.

___


 * [**One to One – Unidirectional**](/jpa/otou.md)
 * [**One to One – Bidirectional**](/jpa/otob.md)
 * [**OneToMany – Unidirectional**](/jpa/otmu.md)
 * [**OneToMany – Bidirectional**](/jpa/otmb.md)
 * [**Many To One – Bidirectional**](/jpa/mto.md)
 * [**ManyToMany**](/jpa/mtmb.md)
 
