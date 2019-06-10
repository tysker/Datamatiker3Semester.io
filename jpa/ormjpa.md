[**HOME**](/index.md) | [**JPA**](/jpa/jpa.md)


## Create New JPA Project

	1. create a new Database in workbench
	2. create new Maven project in netbeans
	3. create new entyties (classes)
		a. remember to change long to Integer at primary key
		b. change if not said otherwise, GenerationType.Auto to GenerationType.IDENTITY
		c. add new private variable to your classes
		d. add getter and setters
		e. add two constructors. One has to be empty and the nr 2 includes variables minus generated key.
	4. add new package called utils 
		a. included a java class called SchemaBuilder. Add a main method to the class and add the following line: Persistence.generateSchema("NAME_OF YOUR_PU", null);
		b. also include a new class for each entity in your entiy package called Tester.
	5. Remember to ckeck your persistance file which Table Generation Strategy you choose. "Create, Drop and create, none"
		a. check if all entity classes are included in the "Include Entity Classes:" Box
	6. SchemeBuilder
		a. SchemaBuilder java class i utils package. add   Persistence.generateSchema("pu", null);
		
	7. Tester class
		a. create a main methode
		b. create EntityManagerFactory emf = Persistence.createEntityManagerFactory("pu");
		c. create EntityManager em = emf.createEntityManager();
		d. try {}
		e. em.getTransaction().begin(); 
		f. em.persist(object);
		g. em.getTransaction().commit();
		h. finally{em.close();}
	8. Facade
		a. create package dbfacade
		b. EntityManagerFactory emf;
		public CustomerFacade(EntityManagerFactory emf){this.emf = emf;}
		c. for each method use:
		EntityManager em = getEntityManager();
		try{
		  // Use the entity manager  
		}finally{
		  em.close();
		}
	9. Remember dependencies:
		a. mysql-connector

  
 

