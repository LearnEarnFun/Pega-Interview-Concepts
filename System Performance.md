# System Performance

## A screen that has a D page reference is taking time to load in production environment. What are all the considerations need to look at?

* Number of filters referred in the report definition of the corresponding D page. 
* Ensure all filter references are optimised properties. 
* Any filter queries that are not exact match [Contains search, greater than equals etc...,] results in performance related issues. 
* Number of joins referred in the report definition - Recommendation is to have a maximum of three joins
* Ensure that there are no Left and Right Outer joins in the report definition. 
* If there is a clipboard size issue, then limit the D page usage to a single page. 
* Verify the alerts file, if there is any HTTP interaction issues, ***then the alert will show the activity details that is taking more time for the execution***

## How you will improve the System Response Times for interactive users after system startup?

Run the static assembler using  - Configure -> System -> Assembly -> Static Assembler. This static assembler helps to pre-assemble all the rules and cached the rules of the application. This step is useful in the following scenarios:

* After system start-up, especially after new ruleset versions imported into the system
* Many rules have changed 
* User profiles have changed to allow new or different ruleset versions 
