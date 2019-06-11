[**HOME**](../index.md)



### @Path

    @GET
    @Path("availablecars/{week}/{address}")
    @Produces(MediaType.APPLICATION_JSON)
    public Response carsByWeekAndAddress(@PathParam("week") int week, @PathParam("address") String address)
    
### @Query

