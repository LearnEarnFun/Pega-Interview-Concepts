# PEGA 8 New Features

## How the Agents got modified in PEGA 8?

1. __Standard Agents  - Queue Processors__ 
2. __Advaneced Agents - Job Scheduler__

- ***Queue Processor rules support higher scaling throughput than agents. Each queue process manages across 20 partitions, which means that Queue Processor rules can support up to 20 separate processing threads simultaneously with no conflict.***

For above two rule resolution configurations, access group is defined in the ASYNCPROCESSOR requestor type.