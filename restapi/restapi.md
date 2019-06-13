[**HOME**](../index.md)

## SET UP Blank Maven Project

	1. Maven Web application
	2. Install jersey-bundle dependency and com.google.gson
	3. create new package
	4. choose Restfull Web Services from Patterns
		a. simple root ressource
		b. Path: for eksample Customer
		c. application/json
	5. change "webesources" til "api" I ApplicationConfig.java
	6. change path in the other class to lower case
	7. add Path to Get method @Path("/all") (indstead of all you can anything else)
	8. Gson gson = new GsonBuilder().setPrettyPrinting().create(); i entity classen.
	9. Clean and Build
	10. Response.ok().entity(gson.toJson(List eller Object)).build();      
		a. ok() = 200 Code
		b. entity() =  http Responds Body


### @Path

    @GET
    @Path("availablecars/{week}/{address}")
    @Produces(MediaType.APPLICATION_JSON)
    public Response carsByWeekAndAddress(@PathParam("week") int week, @PathParam("address") String address)
    
### @Query

    @GET
    @Produces(MediaType.APPLICATION_XML)
    public Response getListofPersonsl(@QueryParam("startId") int startId, @QueryParam("generate") int generate) {
        //
        List<Person> persons = Generator.generate(generate, startId);
        return Response.ok().entity(gson.toJson(persons)).build();
    }


### Persistance Eksempler

    public Customer addCustomer(Customer c){
            EntityManager em = emf.createEntityManager();

            try{
                em.getTransaction().begin();
                em.persist(c);
                em.getTransaction().commit();
                return c;
            }finally{
                em.close();
            }

        }
        
        
### Test

    @Before
    public void setUp() {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("pu");
        EntityManager em = emf.createEntityManager();
        try {
            System.out.println("delete");
            em.getTransaction().begin();
            em.createQuery("DELETE FROM Customer").executeUpdate();
            em.getTransaction().commit();
        } finally {
            em.close();
        }

    }


### Generator Eksample

    public class Generator {

    private static String[] fname = {"Hans", "Gitte", "Claus", "Stefan", "Jörg"};
    private static String[] lname = {"Schmidt", "Mueller", "Oertel", "Hansen", "Jensen"};

    //creates a list of Persons
    public static List<Person> generate(int generate, int id) {
        List<Person> persons = new ArrayList();
        Person person;
        for (int j = id; j < generate+1; j++) {
            String firstName = fname[(int) Math.floor(Math.random() * fname.length)];
            String lastName = lname[(int) Math.floor(Math.random() * fname.length)];
            int random = (int) ((Math.random() * 53)) + 17;
            person = new Person(firstName, lastName, j, random);
            persons.add(person);
        }
        return persons;
    }


      // returner en List af persons to en list af json strings entitys
        public static List<String> toJson(List<Person> persons) {
            List<String> personToJson = new ArrayList();

            for (Person p : persons) {
                personToJson.add(new Gson().toJson(p));
            }
            return personToJson;
        }
    
