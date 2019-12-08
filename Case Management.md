# Case Management

## What is the difference between the CorrNew and SendCorrespondence activities?

Call the CorrNew utility activity from a flow to send correspondence if you want flow processing to continue on immediately. Use the flow SendCorrespondence with the flow (subprocess) shape instead if processing needs to wait on correspondence verification.  Neither CorrNew nor SendCorrespondence can be used with correspondence that specifies "Must Edit".  Corrs that require editing can only be created using the correspondence flow actions (SendCorrespondence or Notify).

## How to invoke the Declare Collection rule from an activity?

Use the **Collect** Keyword - followed by the declare collection rule name.

## How to restrict the Wait Shape resume operation for end users?

On the Wait Shape, there is an option to disable the ***Users can choose to continue process***. This will not allow the user to user to perform any action on the Wait assignment. 

## How to propagate the page context data to the Multiple Child Cases that are getting created from the Page List property?

Create Case smart shape is nothing but the pxAddChildWork activity reference. There is a default extension data transform called __pyAddChildWorkDefaults__. It is used to propagate the data to the Child Page Context that is getting created. 

## How the Parent and child cases locking mechanism works?

The locking strategy whatever we defined on the parent case is followed for the current case and to the corresponding child cases. 

__Default locking strategy__ - Locking the case for a single user for defined time. 

__Optimistic locking strategy__ - Allowing multiple users to access and modify the case. 

## How the actual Java Threads or Parallel processing works in PEGA?

__Spin-off && Split For Each__ - are the case shapes treated for parallel processing at the case lifecycle level. 

But, actual Java Thread level parallel processing works using the __QUEUE__ method as part of the activity invocation. 

## What is the difference between the Obj-Save-Cancel and Rollback methods?

Obj-Save-Cancel method cancels the most recent one deferred save. 

Rollback method rollsback all the deferred save operations. 

## How you will handle the flow changes that are in production?

There are three approaches to implement the flow changes that are already in the production.

__Approach #1__: Create distinct flows, and enable the "Creates new work object" to the newly created flows. Remove the "Creates new work object" on the old flows. Implement circumstance to the existing flows. 

Drawbacks:
- If there are more subprocess levels than four then this is not the recommended approach.

__Approach #2__: Move all existing assignments, sub-process and wait shapes to the side of the flow. Inflight case assignments will follow the previous assignments and the new cases will follow the new assignments. 

__Approach #3__: Add tickets to the newly modified flows. Run a bulk processing job to find all outdated assignments in the system. For each assignment, the bulk processing should call ***Work-.OpenAndLockWork***, then call ***Work-.SetTicket*** on the work page.

Pros:
- Newly modified flows are clean

__Approach #4__: Revert the user's ruleset list to original, lower versions when dealing with older assignments

Pros:
- When changes go beyond the flow rules, then this is the only sure approach.

## How will you handle the 10-15 fields changes as part of the screen?

__Approach #1__: If it is very few fields like 3-5, then have to use the ***Field Level Tracking*** feature. It is nothing but the declare trigger. Extend the "pyTrackSecurityChanges" data transform into the appropriate work class. 

__Approach #2__: If it more fiels let's say 10-15, then the approach is different. Populate the required fields into a temporary page or a complete work page. Then convert the page into JSON or XML using the functions - pxConvertPageIntoJSON, pxConvertPageIntoXML. Store the respective string property into a dedicated tablee.