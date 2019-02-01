
## Test, Maven and Travis Guidelines

For specific plug-in information, please go to this page: [Plugins](tek.md)


* **Unit Test all “relevant” public methods via Maven**

1. Create a test package (packagename)
2. Write the tests for each relevant method associated with the Class.
3. For **Maven** to recognize the tests add **@Test** above the test-method.


* **Exclude integration tests from your unit test, and why this is necessary**

1. Add the plugin "(**maven-surefire-plugin**)" to your POM file, as this one excludes the 'Integrationtests' package.
This is neccessarry in order to run the JUnit tests seperate.


* **Perform integration tests, and only integration tests, via maven’s verify phase**

1. Add the plugin "(**tomcat7-maven-plugin**)" to your POM file as a profile. This one has two executions, pre & post which starts an        embedded tomcat server up before tests, and shutdowns the server after the tests are done.


*  **How and what to do, to test a Tomcat based WEB-API, via maven’s verify phase**

1. Stay in the project folder and run the command "**mvn verify** "(-P <Profilename>)"


* **How and what to do, to deploy your code via maven**

1. Stay in the project folder and run the command "**mvn tomcat7:deploy** "(-P <Profilename>)"


* **How and what to do, to integrate your project with Travis**

1. Create a Travis-ci account with your GitHub. 
2. Flip the switch on the repositories to integrate with.


