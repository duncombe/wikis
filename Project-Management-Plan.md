This document describes the procedures we'll adhere to in carrying out the project.  It is comprehensive in that it includes management of all relevant knowledge areas, with the exception of cost management. Areas addressed by this document include the following:
* Scope Management: Track Development of [Test Themes](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes)
* Time Management: Track [Milestones](https://github.com/ioos/system-test/issues/milestones)
* Quality Management: Track [System-Test Metrics](https://github.com/ioos/system-test/graphs)
* Communication Management: Track [Issues](../issues)
* Risk Management 
* Integration Management: Track List of [Services Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs)

This document does not address procurement management, as there are no procurement actions planned for the project.


# Goals and Objectives

The Integrated Ocean Observing System (IOOS) is a federal, regional, private sector, and academic partnership that tracks, predicts, manages, and adapts to changes in our marine environments. The Data Management and Communications (DMAC) project of IOOS strives to deliver real-time, delayed-mode, and historical data from physical, chemical and biological data. Those data may be stored in repositories or come directly from sensors operated by academic, state, regional and federal members of IOOS.  The DMAC project has three objectives:

1.  Standardize data structure and syntax across sensors and repositories to make data discovery and retrieval easier for researchers and policy makers.
2.  Enhance open source search and retrieval software to provide a library of tools that have been tested and proven to work in discovering and retrieving IOOS data.
3.  Improve the accessibility of IOOS data to multiple scientific disciplines, including, but not limited to, oceanography, meteorology, marine biology and climatology.


The Data Management and Communications (DMAC) System Integration Test project is instrumental to the DMAC program’s overall objectives.  It represents the means by which the DMAC program defines its objectives and tracks its progress towards them.  The DMAC System Integration Test will:

1.  Create test cases which incorporate multiple IOOS Regions and partners, cover a large geographic scope, employ multiple types of data, and cross scientific disciplines. These test cases demonstrate that data consumers can use DMAC data discovery and access services to get IOOS data in a repeatable way. This is considered the baseline 
2.  Apply these test cases to real world problems related to Extreme Events and Ecologically Sustainable Marine Energy Planning
3.  Compile a set of prioritized fixes and enhancements to DMAC data discovery and access services
4.  Complete highest priority fixes and enhancements
5.  Publish the test cases to encourage community education and involvement in IOOS
6.  Demonstrate the added value of federal and non-federal data integration by IOOS data management to the ocean and coastal community
7.  Ensure that we can repeat the assessment easily to measure progress over time





# Scope

The scope of the test is divided among three categories:
  1.  Subject matter scope: [Test Themes](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes)
  2.  Data Content Scope: [Services Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs) 
  3.  Technology Scope: [Custom Wakari Environments](https://github.com/ioos/system-test/tree/master/wakari)

* Using python clients exclusively (TODO: Provide a list of the packages and links to the conda.spec file that we'll use)
* *_Editors note: we will note be testing or deploying any push technologies so Alerts are out of scope for DMAC and for this project._*

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
