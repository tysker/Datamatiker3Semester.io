[**HOME**](index.md) | [**JPA**](jpa.md)


# One to One – Bidirectional


Creating a bidirectional one to one relationship between two tables (in this exercise customer and address) will create a foreign key on the table pointing to the associated table’s PK. This will ensure a link between the tables. 
But opposite of a unidirectional relationship, we can go both ways when selecting data between the tables, as both classes implements an object of each other. We made a @OneToOne relation between customer and address, with customer being the owner of the relationship. But the other class address, now has a @OneToOne(mappedBy = "address") and private Customer customer which shows that the address class now holds a object of the customer class. Therefore, the relationship is in both directions.


**!!NOTE!!**
Defining the direction of the relationship between entities has no impact on the database mapping!!!!
