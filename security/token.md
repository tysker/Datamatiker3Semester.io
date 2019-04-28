[**SECURITY**](security.md)


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


1. The first section is a header that describes the token.
2. The second section is a payload which contains all the information that is needed.
3. The third section is a signature hash that can be used to verify the integrity of the token (if you have the secret key that was used to sign it).

They are all base64 encoded. (encoded and not encrypted!!!!)

**Header:**

    {
    "typ": "JWT"
    "alg": "HS256"
    }
    
alg = Algorithem => HS256 or RS256 or ES384 or ....  

**Payload:** 

Payload is a JSON Object:


    {
    "iss": "ABC Service App",
    "name" "Jörg"
    "admin": "false"
    and a lot more can be added.........
    }
    
_(iss = issuer)_

**contains:** 
* Who this person is (sub, short for subject)
* What this person can access with this token (scope)
* When the token expires (exp)
* Who issued the token (iss, short for issuer)

These declarations are called ‘claims’ because the token creator claims a set of assertions that can be used to ‘know’ things about the subject.

**Signature**

* It's basically the two parts from the token, header and payload hashed.
* A hash of header and payload using a secret!
* If you temper with either of the header or payload, the signature will not match, so the token would be invalid.

_____

## Where to store JWT's

* HTML5 Web Storage (localStorage or sessionStorage)
* Cookies

Link:
* [**WHERE TO STORE!**](https://stormpath.com/blog/where-to-store-your-jwts-cookies-vs-html5-web-storage)

____


## Tokens LifeCycle example

1. **Client** = Request tokken by providing authentic credentials.

2. **Server** = 

       *  check credential 
       *  create JWT token
       
3. **Server** = Send JWT to client or error if not authorized.

4. **Client** = 

       *  verify  token (optional)
       *  extract information for App usage (optional)
       *  persist token at client side.

5. **Client** = Use same persisted tokken for subsequent calls to serve.

6. Verify token for all subsequent request. The same tokken will be used for all subsequent request.

7. If the token is valid, respond or return error.



