# Reporting

## How you will improve the report definition performance?

Verify the following best practices as part of the report definition

1. ***Try to reduce the number of index joins*** (for example, if required, create multiple report definitions and logically determine the report definition name using decision table, etc...)

2. Verify all properties used are exposed as part of the work tables

3. PAGINATION: Verify the number of records that are getting retrieved (If required, implement __pagination__ for the report definition and to have the better peformance)

4. Implement the __Reporting Filter Conditions__ as a section for the report viewer. This will help the user to filter out and select the appropriate record.

## How does the scheduling a report will work?

In the Report Viewer, schedule a report and also subscribers information. Subscribers are the operators who require this report as an email notification. 

Email will sent from the "Default -> Notify" Email account. 