# Why conduct a system test? 

The distributed, service oriented architecture of DMAC has been implemented mostly independently by IOOS partners, using different software approaches and different levels of implementation (e.g. services provided, percent of datasets available via services, percent of datasets registered with the IOOS catalog).
  
The DMAC system integration test  (SIT) will evaluate whether the services we have deployed (i.e. SOS, OPeNDAP, WMS, CS/W) to Federal partners and Regional Associations can solve real world problems. 


# What will the system test achieve?
The DMAC system integration test project will assesses the maturity of DMAC implementation across IOOS Regional Associations and partner federal agencies.  The DMAC System Integration Test will:

1. Create test cases which incorporate multiple IOOS Regions and partners, cover a large geographic scope, employ multiple types of data, and cross scientific disciplines.  These test cases demonstrate that data consumers can use DMAC data discovery and access services to get IOOS data in a repeatable way.   
2. Apply these test cases to real world problems related to Extreme Events and Ecologically Sustainable Marine Energy Planning.
3. Compile a set of prioritized fixes and enhancements to DMAC data discovery and access services
4. Complete highest priority fixes and enhancements
5. Publish the test cases to encourage community education and involvement in IOOS
6. Demonstrate the added value of federal and non-federal data integration by IOOS data management to the ocean and coastal community
7. Ensure that we can repeat the assessment easily to measure progress over time


* [Project Management Plan](https://github.com/ioos/system-test/wiki/Project-Management-Plan)
* [Test Themes](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes)
* [Service Registries and Catalogs](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs)
* [References](https://github.com/ioos/system-test/wiki/References)

# What will the test look like?
  Elements of a successful system integration test include: 
*  Includes each of the functionalities that are being developed as part of DMAC currently.  The primary functions include data access services (web services that provide in situ, model or satellite data), discovery services (catalogs and registries providing query and look up functionality), and client tools (software packages that find data using catalogs/registries and download/use data from data access services);
*  Emphasizes the process over the product, at least at first.  A system integration test is a step towards creating a robust system.  In exercising an integration test we EXPECT problems.  The test must rigorously capture the problems and document the conditions that caused the problems.  These problems may be fixed in the course of the project but ONLY if it can be done with sound engineering and design.  If shortcuts and workarounds are employed to get to the end product then the system will likely fail again when it encounters small (or large) variations upon the initial failure conditions. In the process of rigorously testing and documenting the system, the end product will be improved;
*  Measures everything.  For reasons described above, the system integration test must document the conditions of the test;
*  Uses the DMAC services as they were intended to be used and without shortcuts.  In typical usage patterns there is always a discovery step where the user is searching for unknown data assets.  If this step is skipped and known data sources are hardcoded into the test, then the efficacy of the test is compromised.  It must exercise the system in total;
*  It should combine two or more feature types.  Technologies for in situ data types and gridded model data types differ slightly.  Both should be included in a test to ensure the test is not biased toward one of the preferred data types;
*  It should be focused on a scientific or societal problem with "large" geographic scope.  The capabilities of regional associations and federal agencies varies regionally but the system is only as strong as its weakest link.  The test should cross several regional boundaries in order to not be biased;
*  Ideally it should require data that crosses disciplinary boundaries.  Biology and physical oceanography for example;
*  With all of these characteristics, the test should still be of limited scope.  Do not stretch the capabilities of the system components beyond their advertised capabilities;
*  The project should not require new scientific insights or be designed to enable research.  The object is to test the combined capabilities of the DMAC system, not to challenge the scientific users of the system.  The system cannot grow to support the full creativity of the scientific enterprise until some of the more basic engineering concerns are tested;
*  The system test should include one or more performance requirements or metrics.  The system components thus far have been designed primarily with functional requirements in mind.  Relatively less attention has been paid to the performance characteristics of the combined systems (think about timing or volume restrictions like downloading an entire HD movie over a 3G cell connection);
*  The test shouldn't be overly reliant on components over which we have no control.  If a critical failure point is in another agency then it's possible that the test cannot actually proceed without their cooperation;

