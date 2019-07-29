# Integration Management

## What are the different types of authentications allowed as part of connecting to a service provided?

***BASIC Authentication*** is used to store the external service provided user name and password in an Authentication profile, and refer the same in the connect rule forms. 

***OAuth Authentication*** is a two step process verification
Step 1: Register the OAuth2.0 Client Registration rule with the service provider Client ID and Client Secret Key.
Step 2: Retrieve the token using the OAuth Service Provider service.

How it works? Connect Service will retrieve the token using the provided Client ID and Client Secret Key, then the token is passed as part of the actual service call in header. Token will have an expiry defined at the service provider end. Majority of the Google, AWS, and facebook products comes with this type of authentication. 
