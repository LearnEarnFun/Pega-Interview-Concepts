# Integration Management

## What are the different types of authentications allowed as part of connecting to a service provided?

***BASIC Authentication*** is used to store the external service provided user name and password in an Authentication profile, and refer the same in the connect rule forms. 

***OAuth Authentication*** is a two step process verification
Step 1: Register the OAuth2.0 Client Registration rule with the service provider Client ID and Client Secret Key.
Step 2: Retrieve the token using the OAuth Service Provider service.

How it works? Connect Service will retrieve the token using the provided Client ID and Client Secret Key, then the token is passed as part of the actual service call in header. Token will have an expiry defined at the service provider end. Majority of the Google, AWS, and facebook products comes with this type of authentication. 

## How is the SSO Authentication is implemented through SAML Integration?

***SSO- Authentication Service*** is used to login through windows active directory credentials. 
1. Provide __Identify Provider Metadata Information__ that we got from Windows Active Directory - Entity Identificaiton URL, Login Location and Logout Location. This information is specific to the Windows Active Directory environment. 
2. In the mapping tab, map the information from the SAML fields to the OperatorID Page fields 
3. There are two activities that are present - Pre-authentication and Post-authentication processing activities. In the Post-authenticaiton processing activity, we can perform the save of the OperatorID Page to save information mapping from SAML file to the OperatorID Page.  

## What is the CORS (Cross Origin Resource Sharing) Policy?

The __Cross Origin Resource Sharing__ policy is allowed to defined the allowed origins (kind of whitelisting the IP's), allowed headers, allowed methods, and credential usage for a specific REST Service. 

Map the CORS record to a service rule.

## What are the security policies as part of the Integrations?

## What are the connect and service request processors?

The connect and service request processors are used for the asynchronous processing of connect-soap or service-soap calls.
These are the queue data instances, processed by the PEGA-Intsvcs agents. 
