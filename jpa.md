

# Java Persistance Aplication



**Importen Links**

* <a href="https://www.objectdb.com/api/java/jpa/annotations" target="_blank">**List of ALL JPA-annotations**</a>
* <a href="https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html" target="_blank">**EntityManager - Method Summary**</a>
 * <a href="https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html#persist(java.lang.Object)" target="_blank">**Persist - Merge- Remove - Find**</a>


**Notes**

* We only use annotation based mappings.
* 	• The Java Persistence API (JPA) is a Java specification for accessing, persisting, and managing data between Java objects / classes and a relational database.
* You must put the annotation on the get method, not the set method. 

**Mapping**

* The first thing that you need to do to persist something in Java is define how it is to be persisted. This is called the mapping process 

https://docs.oracle.com/javaee/5/api/javax/persistence/EntityManager.html#persist(java.lang.Object)
**Persisting**

* The EntityManager represents the application session or dialog with the database.
* The EntityManager provides an API for all required persistence operations. These include the following CRUD operations:
  1. persist (INSERT)
  2. merge (UPDATE)
  3. remove (DELETE)
  4. find (SELECT)


