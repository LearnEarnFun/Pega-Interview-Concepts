# Data Management

## How to pre-load the data page before the screen UI renders?
In the pre-activity of the flow action, have to use the **LOAD-DATAPAGE** PEGA API method to load the data pages before the screen UI renders. If there are multiple D Pages used as part of the screen, then configure the *asynchronous data page pool name* as part of the LOAD-DATAPAGE PEGA API method and use the Connect-Wait subsequently to invoke multiple D Pages. 

## What is the implementation approach for a 50K RECORDS data for a parameterized datapage approach?

1. Load all 50K Records into a single node level datapage 
2. For the parameter data pages access, load the records from the node level datapage

***The above approach reduces the number of database calls for the different parameters datapage retrievals.***

## How the node-level datapage is loaded?

For a node-level datapage, a new requestor is created with the access group associated with the data page to load the data page. The access group of the requestor determines the ruleset to use and the security context for the rule resolution during the load. 

***Note: PEGA Recommendation is to create a separate access group for the node level data page loads. This will provides the security for the requestor that gets created for the loads.*** 

## How the page limits works in the data pages?

Page limits

For read-only data pages with a scope of Requestor or Node, select the Clear pages after non-use check box to force the system to delete the clipboard instances of the data page after an interval passes with no access. Subsequent attempts by a requestor to access the data pages cause the pages to reload. ***This setting does not apply to editable data pages.***

When selected, this setting has different effects depending on the scope of the data page:

__Requestor scope__ – The data page instance that is created when any thread refers to the data page is removed when there are no more threads referring to it.

__Node scope__ – The system checks the Reload if older than fields on the Load Management tab of the data page rule. If the fields are blank, the system uses the value of the Dynamic System Setting DeclarePages/DefaultIdleTimeSeconds, which is set by default to 86400 seconds, or one day.

***Note: Read-only data pages are never passivated. If a requestor or thread is idle and gets passivated, all read-only data pages in that requestor or thread are cleared and reloaded the next time they are referenced, whether or not Clear pages after non-use is selected.***

## What are the different types of data pages?

There are three different types of data pages

1. __Read-only__: Read-only data pages can be modified during the page load and in the post-processing activities
2. __Editable__: Initial data page opens up in the read-write mode. Editable is applicable for Thread and Requestor level data pages. 
3. __Savable__: Savable data page saves the data to the database. 