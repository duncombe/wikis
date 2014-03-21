# DMAC Overview

The DMAC integration testing project will assesses the maturity of DMAC implementation across IOOS Regional Associations and partner federal agencies. The DMAC System Integration Test will:

1. Create test cases which incorporate multiple IOOS Regions and partners, cover a large geographic scope, employ multiple types of data, and cross scientific disciplines. These test cases demonstrate that data consumers can use DMAC data discovery and access services to get IOOS data in a repeatable way. This is considered the baseline.
2. Apply these test cases to real world problems related to Extreme Events and Ecologically Sustainable Marine Energy Planning.
3. Compile a set of prioritized fixes and enhancements to DMAC data discovery and access services
4. Complete highest priority fixes and enhancements
5. Publish the test cases to encourage community education and involvement in IOOS
6. Demonstrate the added value of federal and non-federal data integration by IOOS data management to the ocean and coastal community
7. Ensure that we can repeat the assessment easily to measure progress over time

The entire project is organized into phases or focus areas called themes. Themes will focus on a large problem area and will be used to identify common problems or needs commonly encountered by data consumers who work within these theme areas. These theme areas are similar to the GEOSS societal benefit areas.
You can read more about the development and use of Test Themes [here](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes).

# Core Processes of DMAC Testing
DMAC testing includes three core processes:

* Discovery: Surveying one or more data registries to ascertain what data are available in what format(s).
* Access:  Getting at some or all of discovered data across one or more repositories.
* Use:  Inputting accessed data into a known algorithm to determine if the algorithm can use the accessed data to generate meaningful, expected results.

# Tester Responsibilities
DMAC testing is as much about discovery as it is about verification and validation.  The objective of the first round of testing is to identify issues associated with the discovery, access and use processes, using a set of registries and repositories known to contain properly formatted data and metadata, and client scripts that are known to produce certain types of results.  

Tests are oriented around several major themes:
* Baseline Assessment
* Extreme Events
* Ecologically Sustainable Marine Energy Planning
* Monitoring & Regulation of Fisheries

The test themes are described in more detail on the [Development of Test Themes wiki page.](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes)




Issues identified during the first round of testing will be logged, categorized, prioritized, and assigned.  Each developer/tester will be assigned a number of issues.  The developer/tester will perform the following for each issue:
* Research the issue to clarify its scope and identify its cause
* Determine if there is a solution that can be implemented without a major expenditure of time and effort
* Implement the solution if it is viable
* Regression test the solution to ensure that it works correctly and does not introduce other issues
* Close the issue if the regression test is successful