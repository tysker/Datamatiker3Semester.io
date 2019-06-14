[**HOME**](../index.md)

## SET UP Blank Maven Project

	1. Maven Web application
	2. Install jersey-bundle dependency and com.google.gson
	3. create new packages = dto, entity, facade, rest, utils
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

### Setup Response Headers

	1. New package called filter
	2. New Java class called ResponseFilter
	3. Insert this code below
	4. Remember those two annotaions
		@PreMatching
		@Provider
		
		
	@PreMatching
	@Provider
	public class ResponseFilter implements ContainerResponseFilter {
	
	    @Override
	    public void filter(ContainerRequestContext requestCtx, ContainerResponseContext res)
	            throws IOException {
	        res.getHeaders().add("Access-Control-Allow-Origin", "*");
	        res.getHeaders().add("Access-Control-Allow-Credentials", "true");
	        res.getHeaders().add("Access-Control-Allow-Methods", "GET, POST, DELETE, PUT");
	        res.getHeaders().add("Access-Control-Allow-Headers", "Origin, Accept, Content-Type, Authorization,x-access-token");
	    }
	}
	
	5. Rememeber to delete jersey-bundel from your pom file!!
	
	6. add those to dependencies to your pom file:
	
	<dependency>
	    <groupId>org.glassfish.jersey.containers</groupId>
	    <artifactId>jersey-container-servlet</artifactId>
	    <version>2.26</version>
	</dependency>
	<dependency>
	    <groupId>org.glassfish.jersey.inject</groupId>
	    <artifactId>jersey-hk2</artifactId>
	    <version>2.26</version>
	</dependency>
	
	7. Alternative you can use this in your Ressource class
	
	@GET
	    @Produces(MediaType.APPLICATION_JSON)
	    public Response getPersons() {
	        //TODO return proper representation object
	        return Response.ok()
	                .header("Access-Control-Allow-Origin", "*")
	                .header("Access-Control-Allow-Credentials", "true")
	                .header("Access-Control-Allow-Headers","origin, content-type, accept, authorization")
	                .header("Access-Control-Allow-Methods","GET, POST, PUT, DELETE, OPTIONS, HEAD")
	                .entity(gson.toJson(df.getAllPersons())).build();
	    }
	8. Add a Request Filter
	
	package filter;
	
	import java.io.IOException;
	import java.util.logging.Logger;
	import javax.ws.rs.container.ContainerRequestContext;
	import javax.ws.rs.container.ContainerRequestFilter;
	import javax.ws.rs.container.PreMatching;
	import javax.ws.rs.core.Response;
	import javax.ws.rs.ext.Provider;
	
	@Provider  //This will ensure that the filter is used "automatically"
	@PreMatching
	public class RequestFilter implements ContainerRequestFilter {
	
	    private final static Logger log = Logger.getLogger(RequestFilter.class.getName());
	
	    @Override
	    public void filter(ContainerRequestContext requestCtx) throws IOException {
	        // When HttpMethod comes as OPTIONS, just acknowledge that it accepts...
	        if (requestCtx.getRequest().getMethod().equals("OPTIONS")) {
	            log.info("HTTP Method (OPTIONS) - Detected!");
	            // Just send a OK response back to the browser.
	            // The response goes through the chain of applicable response filters.
	            requestCtx.abortWith(Response.status(Response.Status.OK).build());
	        }
	    }
	}
	
	

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
    
