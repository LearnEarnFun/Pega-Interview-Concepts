# Security Management

## What is Data Encryption in PEGA?

If the critical information is getting saved in PEGA Database as an exposed property in the work tables, then the preferred approach is as follows:

    1. Create a cipher class pointing the database using the PEGA media files that comes with product 
    2. Using the same cipher generator PEGA media files, upload the generated JAR into the PEGA database tables 
    3. Navigate to the Data Encrption landing page, refer to the generated cipher class and activate the Data Encryption

## What is the Access Control Policy and Access Control Policy Condition?

__Access Control Policy__ or __Attribute based access control__ is used to restrict the user to access the specific instance of a class (Assign-, Work- and Data-) classes. The actions that can be restricted are READ, UPDATE, DISCOVER, DELETE, PROPERTYREAD, AND PROPERTYENCRYPT.

The __Access Control Policy Conditions__ uses the When rules - comparing the class instance attribute values to the clipboard, or operator level values. 

It is different from the __role based access restrictions__. This restriction is at the class instance level. 
