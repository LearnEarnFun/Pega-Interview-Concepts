# Data Management

## How to pre-load the data page before the screen UI renders?
In the pre-activity of the flow action, have to use the LOAD-DATAPAGE PEGA API method to load the data pages before the screen UI renders. If there are multiple D Pages used as part of the screen, then configure the asynchronous data page pool name as part of the LOAD-DATAPAGE PEGA API method and use the Connect-Wait subsequently to invoke multiple D Pages. 
