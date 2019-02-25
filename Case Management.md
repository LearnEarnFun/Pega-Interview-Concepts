# Case Management

## What is the difference between the CorrNew and SendCorrespondence activities?

Call the CorrNew utility activity from a flow to send correspondence if you want flow processing to continue on immediately. Use the flow SendCorrespondence with the flow (subprocess) shape instead if processing needs to wait on correspondence verification.  Neither CorrNew nor SendCorrespondence can be used with correspondence that specifies "Must Edit".  Corrs that require editing can only be created using the correspondence flow actions (SendCorrespondence or Notify).
