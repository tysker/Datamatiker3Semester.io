[**HOME**](index.md)

# Java Persistance Aplication

**Slides**




**Importen Links**

* <a href="https://www.objectdb.com/api/java/jpa/annotations" target="_blank">**List of ALL JPA-annotations**</a>
* <a href="https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html" target="_blank">**EntityManager - Method Summary**</a>
 * <a href="https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html#persist(java.lang.Object)" target="_blank">**Persist-Merge-Remove-Find**</a>
 
 
 **Requirements for Entity Classes**
* The class must be annotated with the @Entity annotation.
* The class must have (at least) a public or protected, no-argument constructor. 
* The class must not be declared final. No methods or persistent instance variables must be declared final.
* If an entity instance is passed by value as a detached object, the class must implement the Serializable interface.
* Entities may extend both entity and non-entity classes, and non-entity classes may extend entity classes.
* Persistent instance variables must be declared private, protected, or package-private and can be accessed directly only by the entity class's methods. Clients must access the entity's state through accessor or business methods.



**Notes**

* We only use annotation based mappings.
* The Java Persistence API (JPA) is a Java specification for accessing, persisting, and managing data between Java objects / classes and a relational database.
* You must put the annotation on the get method, not the set method. 
* The **EntityManager.remove()** operation is used to delete an object from the database. remove does not directly delete the object from the database, it marks the object to be deleted in the persistence context (transaction). When the transaction is committed, or if the persistence context is flushed, then the object will be deleted from the database.
* **NEVER** commit your persistence.xml file. Add persistence.xml to your .gitignore file


**Mapping**

* The first thing that you need to do to persist something in Java is define how it is to be persisted. This is called the mapping process 


**Persisting**

* The EntityManager represents the application session or dialog with the database.
* The EntityManager provides an API for all required persistence operations. These include the following CRUD operations:
  1. persist (INSERT)
  2. merge (UPDATE)
  3. remove (DELETE)
  4. find (SELECT)
* The EntityManager is an object-oriented API, so does not map directly onto database SQL or DML operations. For example to update an object, you just need to read the object and change its state through its set methods, and then call commit on the transaction. The EntityManager figures out which objects you changed and performs the correct updates to the database, there is no explicit update operation in JPA.


