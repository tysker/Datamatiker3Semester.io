[**HOME**](index.md)



# OneToMany – Unidirectional


Relations like this will always need one of the entities to hold a kind of list to hold multiple objects of the other entity it relates to. 
By default, the IDE (NetBeans) will create a join table to hold this relation, but this does not make sense, therefore ALWAYS use **JoinColumn for this.** 

In example, I wrote the @JoinColumn at customer class, with the mappedBy called “customer_id”, this means that the address table will now have a column called customer_id to link a address to a customer.
Unidirectional means that the direction of the relationship goes one way, and in my exercise I chose customer to take ownership of the relationship. Which means that my customer entity holds a list of addresses.


https://en.wikibooks.org/wiki/Java_Persistence/OneToMany
