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