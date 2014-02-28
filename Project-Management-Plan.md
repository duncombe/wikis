This document describes the procedures we'll adhere to in carrying out the project.  It is comprehensive in that it includes management of all relevant knowledge areas, with the exception of cost management. Areas addressed by this document include the following:
* Scope Management
* Time Management: [Track Milestones](https://github.com/ioos/system-test/issues/milestones)
* Quality Management
* Human Resource Management ([Hannah's Weekly Updates](https://github.com/ioos/system-test/wiki/Hannah-Weekly-Updates))
* Communication Management [Issues](../issues)
* Risk Management 
* Integration Management

This document does not address procurement management, as there are no procurement actions planned for the project.


# Goals and Objectives

The Integrated Ocean Observing System (IOOS) is a federal, regional, private sector, and academic partnership that tracks, predicts, manages, and adapts to changes in our marine environments. The Data Management and Communications (DMAC) project of IOOS strives to deliver real-time, delayed-mode, and historical data from physical, chemical and biological data. Those data may be stored in repositories or come directly from sensors operated by academic, state, regional and federal members of IOOS.  The DMAC project has three objectives:
1. Standardize data structure and syntax across sensors and repositories to make data discovery and retrieval easier for researchers and policy makers.
2. Enhance open source search and retrieval software to provide a library of tools that have been tested and proven to work in discovering and retrieving IOOS data.
3. Improve the accessibility of IOOS data to multiple scientific disciplines, including, but not limited to, oceanography, meteorology, marine biology and climatology.

The Data Management and Communications (DMAC) System Integration Test project is instrumental to the DMAC program’s overall objectives.  It represents the means by which the DMAC program defines its objectives and tracks its progress towards them.  The DMAC System Integration Test will:
1.	Create test cases that demonstrate that data consumers can use the DMAC data discovery and access services to get data in a repeatable way.  This is considered the baseline.
2. Apply these test cases to real world problems related to Extreme Events and Environmental Impacts associated with Energy Facility Siting (TBD?)
3. Publish an overall maturity percent as measured against XXXXX.  
4. Compile a set of prioritized fixes and enhancements to DMAC data discovery and access services
5. Complete highest  priority fixes and enhancements
6. Publish the test cases in an open collaborative environment to encourage community education and involvement in IOOS
7. Ensure that we can repeat the assessment easily to measure progress over time




# Scope

The Scope of the Systems Integration Test includes several 

The scope of the test can be thought of along several different categories.  First is the subject matter scope and we’ve thus far defined that to be represented by the three larger themes.  Second is the data content scope and we’ve limited that by choosing the number of service registries to consider (Our current draft of that is on the wiki).  Third is the technology scope which we’ve limited by selecting Python as our primary computing environment.  This has the effect of limiting our clients which in turn limits the type of data service we can access.

* Using python clients exclusively (TODO: Provide a list of the packages and links to the conda.spec file that we'll use)
* *_Editors note: we will note be testing or deploying any push technologies so Alerts are out of scope for DMAC and for this project._*

# Schedule
The current official end date for this project is approximately Sep 2014.  Tight timeline to fit it all in!!!

 * Use [Issues](../issues) to manage tasks
 * Use issue labels to identify priority (high medium, low) and functionality (registry, data provider, csw/sos/dap/plotting etc))
 * Use milestones to map tasks to dates in the project plan (Microsoft Project document managed offline by John/Derrick).  Therefore, only Derrick or John will add new milestones.
 * Anyone may initiate issues and anyone may select to work on, or own an issue.  If an issue remains unassigned for too long Derrick will assign it.  
 * Derrick will brief management every three weeks and will summarize project status prior to these meetings.



# Documentation

These wiki pages should serve as working documents that are updated as the project progresses.  Some material will be moved from the wiki to the project site as it matures.  The project site will consist of two types of material.  The first is the blog environment that will be used to publish the actual IPython scripts and the results.  The second is a set of static pages that will contain static project information such as Goals/Objectives, description of the themes, etc.  For the early part of the project we will concentrate on the IPython notebooks until we have a critical mass of material to begin summarizing.  

The project site will ultimately be hosted on github and will be published from the main repository using the [Pelican](http://docs.getpelican.com/en/3.3.0/).  There are several good resources out there explaining how this works.  We've started with [Filipe Fernandes' blog](http://ocefpaf.github.io/blog/2013/12/23/blog/) as the model.