This page describes the procedures we'll adhere to in carrying out the project.

# Goals and Objectives

Develop a vision statement and supporting objectives.  For example, we need a general statement of what we're doing and why.  We also need a statement on how others can participate.  _Use this space to develop the material or link to it from here._




* Phase 1 will focus on an assessment of the known service registries and the client capabilities.  It will develop the basic documentation framework including the static web site, the blog/IPython notebook publication, and the dynamic reporting engine that we'll use to summarize various aspects of the project during the project execution.   This phase will be known as the Baseline Assessment theme.
* Phase 2 will elaborate on the baseline assessment and begin to focus on the scientific themes that form the core of the System Test.
* At least one theme will focus on an extreme event such as severe storms or coastal inundation
* Remaining themes will be selected based on input from the project team or anyone else in the community. See [Scenario Brainstorming](Scenario-Brainstorming) for a list of potential scenarios. 

# Scope

The scope of the test can be thought of along several different categories.  First is the subject matter scope and we’ve thus far defined that to be represented by the three larger themes.  Second is the data content scope and we’ve limited that by choosing the number of service registries to consider (Our current draft of that is on the wiki).  Third is the technology scope which we’ve limited by selecting Python as our primary computing environment.  This has the effect of limiting our clients which in turn limits the type of data service we can access.

* Using python clients exclusively (TODO: Provide a list of the packages and links to the conda.spec file that we'll use)
* *_Editors note: we will note be testing or deploying any push technologies so Alerts are out of scope for DMAC and for this project._*

# Schedule
The current official end date for this project is approximately Sep 2014.  Tight timeline to fit it all in!!!

 * Use [issues](../issues) to manage tasks
 * Use issue labels to identify priority (high medium, low) and functionality (registry, data provider, csw/sos/dap/plotting etc))
 * Use milestones to map tasks to dates in the project plan (Microsoft Project document managed offline by John/Derrick).  Therefore, only Derrick or John will add new milestones.
 * Anyone may initiate issues and anyone may select to work on, or own an issue.  If an issue remains unassigned for too long Derrick will assign it.  
 * Derrick will brief management every three weeks and will summarize project status prior to these meetings.



# Documentation

These wiki pages should serve as working documents that are updated as the project progresses.  Some material will be moved from the wiki to the project site as it matures.  The project site will consist of two types of material.  The first is the blog environment that will be used to publish the actual IPython scripts and the results.  The second is a set of static pages that will contain static project information such as Goals/Objectives, description of the themes, etc.  For the early part of the project we will concentrate on the IPython notebooks until we have a critical mass of material to begin summarizing.  

The project site will ultimately be hosted on github and will be published from the main repository using the [Pelican](http://docs.getpelican.com/en/3.3.0/).  There are several good resources out there explaining how this works.  We've started with [Filipe Fernandes' blog](http://ocefpaf.github.io/blog/2013/12/23/blog/) as the model.
