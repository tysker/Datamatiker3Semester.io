
* [**HOME**](../index.md)
* [**5 Easy Steps to Understanding JSON Web Tokens**](https://medium.com/vandium-software/5-easy-steps-to-understanding-json-web-tokens-jwt-1164c0adfcec)


# JWT - Json Web Token

###  Basics:

* It is a Json object
* self contained. Carries all the information neccesary within itself.
* Mainly used in Web application

___


**Can be passed as...**

* a part of an URL (query string)
* form body parameter
* cookie
* HTTP Header (x-access-token)

___

### JWT Structure

**JWT has 3 sections.**

1. the HEADER
2. the PAYLOAD
3. the SIGNATURE

They are all base64 encoded. (encoded and not encrypted!!!!)

**JSON Header:**

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

**contains:** 
* the information which are needed to transmit
* the information related to token itself
