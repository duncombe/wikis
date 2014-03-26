This document describes the resources and techniques to be used in managing important aspects of the DMAC Integration Test Project.  Areas to be managed, as well as the tools and techniques to be used in managing each area, are described below.

# Scope
The DMAC integration test is organized around major scientific and public policy themes.  Themes contain one or more scenarios that narrow the scope and generate questions that can be used to test the discovery, access and use of metadata and data.  It is important to note that test themes and their constituent parts are living documents that may be modified, based on the advice of subject matter experts and the experience of the testers.  Detailed information on test themes may be found at the [Test Themes](https://github.com/ioos/system-test/wiki/Development-of-Test-Themes) page.

The [Baseline] (https://github.com/ioos/system-test/wiki/Development-of-Test-Themes#theme1) will be fully explored, because it includes basic functionality that underlies all subsequent test themes and their constituent scenarios.  However, it is unlikely that the DMAC Integration Test will be able to fully explore all the other test themes within the project's schedule and budget constraints. Test themes that are not explored will provide the basis for follow-on testing as DMAC features and functions are enhanced in later years.

# Schedule
The project schedule is maintained as a set of Milestones within the DMAC GitHub repository.  Within the [Milestones](https://github.com/ioos/system-test/issues/milestones) section of the DMAC GitHub repository, one or more Issues are associated with each Milestone. To reach a given Milestone all associated Issues must be closed.  Each Milestone had a target date.  GitHub uses the target date of each Milestone to track the scheduling of issues. Be aware that unlike other scheduling software like Microsoft Project,  GitHub does not allow a given Issue or Milestone to have a relationship with an Issue or Milestone that has been scheduled to be completed previously.  In other words, GitHub treats every Issue and Milestone as an indedepndent entity, with no dependencies between any Issues or Milestones. One consequence of this is that GitHub cannot by itself construct a critical path for project activities.  Relationships between Issues and Milestones are handled manually by DMAC project managers.

# Quality Management 
Quality management within the DMAC project is accomplished by treating every work package as an Issue, and requiring the resolution of every Issue to be verified by DMAC project managers before it can be closed.  DMAC project managers are the only ones empowered to close Issues.  The DMAC GitHub repository uses information from the status of Milestones and associated Issues to compile [System-Test Metrics](https://github.com/ioos/system-test/graphs).  DMAC proejctmanagers track each Issue and Milestone to determine if project work packages are being completed on schedule.
 
# Communication
Communication within the DMAC IT project team relies on several channels:
* GitHub Issues,which automatically generate e-mail messages to the person assigned the issue, as well as messages to other people specified by the person who logs the issue.  The DMAC project managers should always be included on the e-mail address list for every GitHub Issue.
* E-mail messages may be exchanged between project members using [G-Mail accounts] (https://mail.google.com/mail/?tab=wm#inbox)  within the noaa.gov domain.
* [GitHub Wiki pages] (https://github.com/ioos/system-test/wiki) such as this one within the DMAC GitHub repository.
* In-person or online meetings using WebEx sessions.


 Track [Issues](../issues)
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