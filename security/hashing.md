
[**SECURITY**](security.md)


# Hasing And Salt

### When using jBcrypt algorithm:

Links:
* [**jBCrypt**](https://www.mindrot.org/projects/jBCrypt/)

### Dependencies

      <dependency>
          <groupId>org.mindrot</groupId>
          <artifactId>jbcrypt</artifactId>
          <version>0.4</version>
       </dependency>
       
### Hash and Salt

      String salt = BCrypt.gensalt();
      this.userPass = BCrypt.hashpw(userPass, salt);


verify

      public boolean verifyPassword(String pw) {
              return (BCrypt.checkpw(pw, userPass));
          }






