This document describes the procedures we'll adhere to in carrying out the project.  Areas addressed by this document include the following:
* Scope: The DMAC integration test is organized around major scientific and public policy themes.  Themes contain one or more scenarios that narrow the scope and generate questions that can be used to test the discovery, access and use of metadata and data.  It is important to note that test themes and their constituent parts are living documents that may be modified, based on the advice of subject matter experts and the experience of the testers.  More information on test themes may be found at the [Test Themes](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes)page.
* Schedule: Track [Milestones](https://github.com/ioos/system-test/issues/milestones)
* Quality Management: Track [System-Test Metrics](https://github.com/ioos/system-test/graphs)
* Communication: Track [Issues](../issues)
* Risk  
* Integration: Track List of [Services Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs)

This document does not address procurement management, as there are no procurement actions planned for the project.


# Goals and Objectives

The DMAC system integration test  (SIT) will evaluate whether the services we have deployed (i.e. SOS, OPeNDAP, WMS, CS/W) to Federal partners and Regional Associations can solve real world problems. 

The DMAC integration testing project will assesses the maturity of DMAC implementation across IOOS Regional Associations and partner federal agencies. The DMAC System Integration Test will:

1. Create test cases which incorporate multiple IOOS Regions and partners, cover a large geographic scope, employ multiple types of data, and cross scientific disciplines. These test cases demonstrate that data consumers can use DMAC data discovery and access services to get IOOS data in a repeatable way.
2. Apply these test cases to real world problems related to Extreme Events and Ecologically Sustainable Marine Energy Planning.
3. Compile a set of prioritized fixes and enhancements to DMAC data discovery and access services
4. Complete highest priority fixes and enhancements
5. Publish the test cases to encourage community education and involvement in IOOS
6. Demonstrate the added value of federal and non-federal data integration by IOOS data management to the ocean and coastal community
7. Ensure that we can repeat the assessment easily to measure progress over time



# Scope

The scope of the test is divided among three categories:
  1.  Subject matter scope: [Test Themes](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes)
  2.  Data Content Scope: [Services Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs) 
  3.  Technology Scope: [Custom Wakari Environments](https://github.com/ioos/system-test/tree/master/wakari)

* Using python clients exclusively (TODO: Provide a list of the packages and links to the conda.spec file that we'll use)
* *_Editors note: we will note be testing or deploying any push technologies so Alerts are out of scope for DMAC and for this project._*

List the mechanism we will use to decide if we fix a bug or defer it.

# Schedule
The current official end date for this project is approximately Sep 2014.  Tight timeline to fit it all in!!!

 * Track [Milestones](https://github.com/ioos/system-test/issues/milestones)
 * Track [Issues](../issues) to manage tasks
 * Use issue labels to identify priority (high medium, low) and functionality (registry, data provider, clients etc))
 * Use milestones to map tasks to dates.
 * Anyone may initiate issues and anyone may select to work on, or own an issue.  If an issue remains unassigned for too long Derrick will assign it.  
 * Derrick will brief management every three weeks and will summarize project status prior to these meetings.



# Documentation

##Documentation Process and Approach:
These wiki pages should serve as working documents that are updated as the project progresses.  Some material will be moved from the wiki to the project site as it matures.  The project site will consist of two types of material:  
  1.  Blog Environment with IPython Scripts and Results using [Pelican](http://docs.getpelican.com/en/3.3.0/)
    * Model: [Filipe Fernandes' blog](http://ocefpaf.github.io/blog/2013/12/23/blog/)      
  2.  [Project Page with Static Documentation](https://github.com/ioos/system-test/wiki)  

For the early part of the project we will concentrate on the IPython notebooks until we have a critical mass of material to begin summarizing.  
