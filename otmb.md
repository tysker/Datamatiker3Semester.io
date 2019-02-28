[**HOME**](index.md) | [**JPA**](jpa.md)



# OneToMany – Bidirectional


This relation means that entity **A** holds a list of entity **B**, while entity **B** holds a single instance of entity **A**. 
In the database this relation is kept with foreign key referring to the other table’s primary key. 

In example, I implemented a **List\<Address\>** on the customer class, and created a **@OneToMany** relation, this forced med to create a new column on the address table to join the two tables on. I called this column customer, which was the default value. 
This will automatically create a **@ManyToOne** relation on the address class, and it will also hold a ‘private Customer customer;’. 
This relation is in both directions, which means that data can be gathered no matter if we have data from customer or address.

When using this modelling and relation, you need to remember to set the link in the code in both ways. Which means that a customer object must have a list of addresses, while the addresses itself also need to have a customer associated with it. 

https://en.wikibooks.org/wiki/Java_Persistence/OneToMany
