# System Administration

## What are the prerequisites to connect to a database?

As part of the datasource configuration in the application server. Following parameters are required

    * DataType
    * Database Driver - Configure driver as part of the classpath of the application server
    * Database Driver Class
    * Database username
    * Database password
    
## How to address the JDBC Connection pooling issues in the application? 

As part of the datasource configuration in the application server *(like the context.xml in the tomcat scenario)*. Need to verify the JDBC Connection parameters like maxTotal connections, maxIdle, maxWaitMillis, removeAbandoned, and removeAbandonedTimeout parameters. 

For example, If we want to address the System getting hanged issue as part of the database query scenarios like report definition execution then need to restrict the maxWaitMillis parameter value to a limited value.

## How you will determine the PEGA License Usage Validation Reports?

There is a PEGA OOTB usage validaiton access group __uvu:user__. The users pointed to this access group will have a portal that provide the list of different license usage validation reports.  