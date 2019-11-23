# Agent Management

## How to improve an Advanced Agent taking more time to process the records?

* Generally, if the performance issue is based on the __System resources availability__, then in a multi-node environment allow this particular agent to run in a dedicated background processing node that is classified [Node classification feature for a cluster environment].

* Consider the scenario of a small applicaiton where there is only one production server. In this particular scenario, consider to have a multiple *** Standard Agents *** as part of the advanced agent processing. Kind of ___Vertical Scaling of Agents in a single application server__. 

## What is the Queue class for a standard agent?

PEGA OOTB comes with __SYSTEM-QUEUE-DEFAULT__ class. We can extend the SYSTEM QUEUE to have a custom queue class as well. The standard agent process the records present in this queue database table. __QUEUE-FOR-AGENT__ method is used for the queue entry as part of the case processing. 