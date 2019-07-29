# Index Management

## How to configure the elastic search in a multi node cluster environment?

* In a cluster environment where we have the node classification feature, the nodes that are classified as **Search** type nodes will store the elastic search files. This nodes are managed via Index Management landing page. Search nodes are synched via port 5432 range. The cluster communication is happened through PEGA default **HazelCast** approach or through a **Apache Ignite** client-server model. 

## How to invoke a report definition that runs on the Elastic Search Files?

* In the class __Rule-Obj-Report-Definition__, there is a process API activity ***pxRetrieveSearchData** that executes the passed report definition name on the elastic search files. Invoke this through an activity and pass the required report definition name as a parameter. __Note:__ The limitation of this type of execution on a search files is that we can refer only scalar properties and page properties. But, for a page list or page group properties index of list is not maintained in the elastic search files created. 

This type of execution improves the performance and reduces the database calls, and reduces database calls. 

## What are the agents involved in creating the index files and syncing across the nodes?

* PEGA-SearchEngine agents - FTSIncrementalIndexer, FTSConflictsHandler are responsible for creating search index files. 