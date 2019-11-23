# Data Management

## How to pre-load the data page before the screen UI renders?
In the pre-activity of the flow action, have to use the **LOAD-DATAPAGE** PEGA API method to load the data pages before the screen UI renders. If there are multiple D Pages used as part of the screen, then configure the *asynchronous data page pool name* as part of the LOAD-DATAPAGE PEGA API method and use the Connect-Wait subsequently to invoke multiple D Pages. 

## What is the implementation approach for a 50K RECORDS data for a parameterized datapage approach?

1. Load all 50K Records into a single node level datapage 
2. For the parameter data pages access, load the records from the node level datapage

***The above approach reduces the number of database calls for the different parameters datapage retrievals.***
