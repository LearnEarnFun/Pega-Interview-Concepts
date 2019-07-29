# Security Management

## What is Data Encryption in PEGA?

If the critical information is getting saved in PEGA Database as an exposed property in the work tables, then the preferred approach is as follows:

    * Create a cipher class pointing the database using the PEGA media files that comes with product 
    * Using the same cipher generator PEGA media files, upload the generated JAR into the PEGA database tables 
    * Navigate to the Data Encrption landing page, refer to the generated cipher class and activate the Data Encryption

