# Application Architecture

## What is the classgroup?

A classgroup is a configuration as part of the class definition that creates a dedicated database table. 


## What is the workpool?

Workpool is nothing but a classgroup that is configured as part of the access group. It is the set of allowed workitems or cases that you can work within an application. When you have multiple workpools, you can switch between the workpools from the application menu.

## What happens if we don't define workpool at the accessgroup level?

The logged-in operator with that corresponding accessgroup cannot see the list of classes in the application explorer and cannot create cases from any of the portals. 

## How you will inherit two PEGA Frameworks into an application?

From PEGA 7.2, we can add the __mutiple built-on applications__ as part of the application definition. This concept can be used for the organisation framework application or to the direct implementation application.

Previous to PEGA 7.2, the concept is single built-on with multiple applicaiton instances to inherit multiple frameworks.

## How you will handle the versioning mechanism for the production ruleset?

1. As the application users updates the delegated rules, for the production rulesets - leave the "Use Checkout" checkbox to blank in the ruleset security definition 

2. The same concept applies for reporting production ruleset as well

## How does the Locale works in PEGA?

In the operator rule form, we need to define the operator locale. If the operator locale field is blank, then the system uses the browser locale.

Locale is useful in displaying the dates, currencies, and the locale specific field values in the application. 

## How is the estimation works as part of the PEGA Application?

Sizing wizard provides the way to do the project estimations. It is navigated through ***Designer Studio -> Application -> Tools -> Sizing***. Sizing is done at the applicaiton level with the respective project methodology. The project methodology includes "Scrum" and "Iterative Waterfall". 

__Scrum Methodology__: Provides the list of tasks that are getting planned for each sprint.  