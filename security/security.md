
* [**HOME**](../index.md)
* [**HASHING AND SALT**](hashing.md)
* [**CORS**](cors.md)
* [**5 Easy Steps to Understanding JSON Web Tokens**](https://medium.com/vandium-software/5-easy-steps-to-understanding-json-web-tokens-jwt-1164c0adfcec)


# JWT - Json Web Token

###  Basics:

* It is a Json object
* It is self contained. Carries all the information neccesary within itself.
* It is mainly used in Web application

___


**Can be passed as...**

* a part of an URL (query string)
* a form, body parameter
* a cookie
* a HTTP Header (x-access-token)

___

### JWT Structure

**JWT has 3 sections.**
The section are divided with a dot in beetwen them:

        eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c


1. the HEADER
2. the PAYLOAD
3. the SIGNATURE

They are all base64 encoded. (encoded and not encrypted!!!!)

**Header:**

    {
    "typ": "JWT"
    "alg": "HS256"
    }
    
alg = Algorithem => HS256 or RS256 or ES384 or ....  

**Payload:** _can also be called "claims"_

Payload is a JSON Object:


    {
    "iss": "ABC Service App",
    "name" "Jörg"
    "admin": "false"
    and a lot more can be added.........
    }
    
_(iss = issuer)_

**contains:** 
* the information which are needed to transmit
* the information related to token itself


**Signature**

* It's basically the two parts from the token, header and payload hashed.
* A hash of header and payload using a secret!
* If you temper with either of the header or payload, the signature will not match, so the tokken would be invalid.


_____

## Tokkens LifeCycle example

1. **Client** = Request tokken by providing authentic credentials.

2. **Server** = 

       *  check credential 
       *  create JWT tokken
       
3. **Server** = Send JWT to client or error if not authorized.

4. **Client** = 

       *  verify  token (optional)
       *  extract information for App usage (optional)
       *  persist tokken at client side.

5. **Client** = Use same persisted tokken for subsequent calls to serve.

6. Verify tokken for all subsequent request. The same tokken will be used for all subsequent request.

7. If the tokken is valid, respond or return error.







