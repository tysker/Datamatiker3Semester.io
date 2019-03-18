[**HOME**](index.md)


**Creating Documentation for the Project:**

The Site Plugin is used to generate a site for the project. The generated site also includes the project's reports that were configured in the POM. 


a) Add this section to your pom-file, just above the properties section.


      <reporting>
          <plugins>
            <plugin>
              <groupId>org.apache.maven.plugins</groupId>
              <artifactId>maven-javadoc-plugin</artifactId>
              <version>3.0.1</version>
              <configuration>
                <show>public</show>
              </configuration>
            </plugin>
          </plugins>
      </reporting>



b) Generate the site info using Maven like this: mvn site

c) Navigate into target→ site→ and double-click the project-info.html file to see the generated information. Make sure that you can find the Javadoc API documentation.

d) Use this <a href="https://maven.apache.org/ref/3.6.0/maven-model/maven.html" target="_blank">**link**</a> and add the necessary  fields to your pom-file to include, as a minimum, the following in the report: name, description, list of developers (name+email), the ciManagement system used (Travis)
























