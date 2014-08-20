# Directions
Please use this page for a weekly stand-up report from each development team.  Once a week, preferably on Thursday, a person appointed by each team should access this page and post a short summary of the team's status. There is no need for lots of detail.  When in doubt, use fewer words.  The stand-ups will become a basis of the agendas of our bi-weekly teleconferences.

NOTE: **Please include links to draft notebooks whenever possible**

Please use the following format:
# Week of [Monday date of the work week] 
## Stand-up for [ASA, Axiom, Name-of-independent contributor]  
#### Accomplishments  
* What we've done in the past week  

#### Anticipated activities  
* What we're planning to do in the coming week 

#### Issues  
* Recurring issues that may span a number of individual issues reported in GitHub  

# Week of 2 June 2014

## Stand-up for Axiom

#### Accomplishments
* Reworked the Scenario 3A goals and notebook to be as more general solution.  Starting with a polygon/bbox/wfs layer, we are now searching all catalogs for overlapping datasets.  This allows the polygon to represent any number of things.
* Moved to the new folder structure via: https://github.com/ioos/system-test/wiki/Contributing-to-the-Project#creating-or-updating-notebooks
* Forked repositories and Will learned a lot about git

#### Anticipated Activities
* Search and discovery of new AOOS CSWs should be good to go (crossed fingers)
* Polygon areas will be used to list available data and access actual numbers (Kyle)
* Develop format to pass to Will for data analysis and graphing

#### Issues
* The WFS server hosting the Important Bird Area polygon is not available in any CSW endpoint.

## Stand-up for ASA

#### Accomplishments
* Install iris on mac using condo
* Use iris to get model data.
* Plot modeled vs obs data in Scenario_A_Model_Obs_Compare_Waves.ipynb  (see pull request https://github.com/ioos/system-test/pull/89)
* Start new notebook for comparing model and obs currents

#### Anticipated Activities
* Implement sub directory structure discussed on 5/30 call
* Organize all notebooks in new sub directories
* Compare model and obs current speed/direction; try bounding boxes in different locations, e.g. near Puerto Rico
* Use Iris to get model data for comparison in Extreme Waves and Water Level notebooks
* Start notebook for extreme current values

#### Issues
* Installing Iris on mac - resolved
* Getting NDBC SOS current data for stations near Puerto Rico such as station 41051 (Still investigating whether this merits an actual issue in GitHub)


# Week of 9 June 2014


## Stand-up for Axiom

All hands company meeting all week.  Not much to report.

#### Accomplishments
* Tested and merged pull requests as needed 
* Reorganized directory structure (https://github.com/ioos/system-test/commit/9b874fcd45892279c604dac56658d29f09311022)

## Stand-up for ASA
#### Accomplishments 
* Sorted out lingering iris install issues.
* Use iris to get modeled water level in Scenario_2A_Water_Level_Bird_Redux.ipynb.
Scenario_2A_Water_Level_Bird_Redux.ipynb Progress Report as a git issue (by Friday)
* Continued development on Scenario_2A_ModelDataCompare_Currents notebook.
* Identified missing HF radar data sets

#### Anticipated Activities:
* Finish currents obs vs model data comparison notebook
* Add model data to extreme waves notebook using iris
* Start winds obs vs model data comparison notebook 

#### Issues
* HF Radar data sets not available (issue addressed and closed in https://github.com/ioos/registry/issues/29#event-130915695)
* SOS stations near Puerto Rico not available from Coops collectors (will create an issue Friday)


## Stand-up for Rich Signell, USGS

# Week of 16 June 2014

## Stand-up for Axiom

Both Will and Kyle on vacation, nothing to report.

## Stand-up for ASA
#### Accomplishments 
* Added model data to extreme water level notebook using iris
* Added model data to extreme waves notebook using iris
* Continued development on Scenario_2A_ModelDataCompare_Currents notebook 

#### Anticipated Activities:
* Finish currents obs vs model data comparison notebook (HFRADAR issue not solved until 6/19, so this activity was on hold much of week of 6/16)
* Continue work on winds model/obs comparison notebook
* Continue development on Scenario_2A_ModelDataCompare_Currents notebook 

#### Issues
* SOS stations near Puerto Rico not available from Coops collectors (will create an issue Friday)
* Potential issue with record length returned from tides and currents needs more investigation before posting as a true issue.

# Week of 23 June 2014

## Stand-up for Axiom
#### Accomplishments
* Added Scenario 3H: polar bears
* Improvements to Scenario 3A, including plotting the bounds of all available datasets found that overlap the given polygon. 

#### Anticipated Activities
* Adding missing scenarios
* Focusing on visual improvements to outstanding and existing scenarios
* Putting Scenario 3A data into Pandas for analysis 

## Stand-up for ASA
#### Accomplishments
* Continued work (almost complete) on currents obs vs model data comparison notebook
	Includes 3d color contour plots of observed currents vs time and depth 
* Start work on extremal analysis currents notebook
* Identified new issues (see below)

#### Anticipated Activities:
* Write progress report for model vs obs waves notebook
* Write progress report for extreme waves notebook
* Complete notebook and write progress report for currents obs vs model data comparison
* Complete notebook and write progress report for extreme currents 

#### Issues: 
* CO-OPS SOS service only allows 4 day current requests https://github.com/ioos/system-test/issues/101
* When looking at DAP endpoints from currents data, unable to discern between model and obs (HFRadar) data sets https://github.com/ioos/system-test/issues/102

# Week of 30 June 2014

## Stand-up for ASA  
#### Accomplishments  
* Progress issue written for Scenario 2a modeled vs obs waves notebook https://github.com/ioos/system-test/issues/105
* Continued work on currents obs vs model data comparison notebook.
* Worked on display of sideways looking ADCPs

#### Anticipated activities  
* Write progress report for extreme waves notebook
* Complete notebook and write progress report for currents obs vs model data comparison
* Complete notebook and write progress report for extreme currents 
 
#### Issues  
* Had some trouble accessing modeled current data with IRIS, which impeded progress with currents obs vs model comparison notebook; resolved


## Stand-up for Axiom  
#### Accomplishments  
* No report

#### Anticipated activities  
* No report

#### Issues  
* No report

## Stand-up for IOOC  
#### Accomplishments  
* What we've done in the past week  

#### Anticipated activities  
* What we're planning to do in the coming week 

#### Issues  
* Recurring issues that may span a number of individual issues reported in GitHub  

# Week of 7 July 2014

## Stand-up for Axiom  
#### Accomplishments  
* Completed the harvesting of the UNIDATA motherlode catalog into a WAF of ISO XML files: http://thredds.axiomalaska.com/iso/unidata/.  Submitted to the ioos.catalog@noaa.gov email list for incorporation into the IOOS registry system (and eventually available via CSW).

#### Anticipated activities  
* Gung-ho on "Theme 1 - Baseline"
* Get Scenario 3A to a point that we can start producing graphs and analysis

#### Issues  
* No report

## Stand-up for ASA  
#### Accomplishments  
* Completed currents obs vs model data comparison [notebook](http://nbviewer.ipython.org/github/ioos/system-test/blob/master/Theme_2_Extreme_Events/Scenario_2A_Coastal_Inundation/Scenario_2A_ModelDataCompare_Currents/Scenario_2A_Model_Obs_Compare_Currents.ipynb) and progress report #113
* Continued progress on [extreme currents notebook](http://nbviewer.ipython.org/github/birdage/system-test/blob/hf_radar/Theme_2_Extreme_Events/Scenario_2A_Coastal_Inundation/Scenario_2A_Extremes_Currents/Scenario_2A_Extreme_Currents.ipynb)
 and progress report #110
* Starting on winds notebook.

#### Anticipated activities  
* Write progress report for extreme waves notebook and add modeled wave data
* Finish extreme currents notebook and progress report
* Complete winds notebook
* Start creating spin off notebooks to demonstrate more functionality such as new data catalogs

 
#### Issues  
* Encountered some challenges getting modeled currents #112
* Retrieving long time series of current data is painful. Getting multiple years of 6 minute data for multiple years results in many requests and huge data sets

# Week of 14 July 2014

## Stand-up for ASA  
#### Accomplishments  
* Completed winds obs vs model data comparison [notebook](http://nbviewer.ipython.org/github/Bobfrat/system-test/blob/winds_notebook/Theme_2_Extreme_Events/Scenario_2A_Coastal_Inundation/Scenario_2A_ModelDataCompare_Winds/Scenario_2A_Model_Obs_Compare_Winds.ipynb) 
* Continued progress on [extreme currents notebook](http://nbviewer.ipython.org/github/birdage/system-test/blob/hf_radar/Theme_2_Extreme_Events/Scenario_2A_Coastal_Inundation/Scenario_2A_Extremes_Currents/Scenario_2A_Extreme_Currents.ipynb)
 and progress report #110
* Identified issues (see below)

#### Anticipated activities  
* Write progress report for extreme waves notebook and add modeled wave data
* Finish extreme currents notebook and progress report
* Write winds notebook progress report
* Start creating spin off notebooks to demonstrate more functionality such as new data catalogs 

#### Issues  
* Issues managing large model grid lat/lon arrays #115
* Need to abstract and standardize DAP interface using IRIS #117
* Some services identified as being difficult to obtain long time series data #116 

# Week of 21 July 2014

## Stand-up for Axiom
#### Accomplishments
* Reviewed Extreme Wind notebook
* Organized Theme 1 notebooks into the agreed upon directory structure

#### Anticipated activities
* Theme 1 progress

#### Issues  
* Suffering from information overload when trying to make progress.
* Documentation is everywhere, some is outdated.


## Stand-up for ASA  
#### Accomplishments
* Continued work on winds notebook, including testing catalogs other than NGDC.  

#### Anticipated activities
* Write progress report for extreme waves notebook and add modeled wave data
* Finish extreme currents notebook and progress report
* Write winds notebook progress report
* Continue creating spin off notebooks to demonstrate more functionality such as new data catalogs 
* Test wind data notebook with additional geographies to determine whether lack of data in other catalogs is location specific.

#### Issues  
* Initial tests of other catalogs (to find wind data) did not yield any results will investigate further (e.g. for other geographies) before documenting in a progress report

# Week of 28 July 2014
## Stand-up for Axiom
#### Accomplishments
* Began a dissolved oxygen discovery notebook
* Began a nutrients notebook (but very skeletal)
* Updated Wiki for Theme 1 Baseline events

#### Anticipated activities
* Working on dissolved oxygen discovery vs pyoos
* The python stalwart will cross-check the noob's code

#### Issues
* NERRS stations are a great resource with known dissolved oxygen data, but don't use a CF standard name for discovery and require IP registration for data access. Emilio was working with Dan Ramage to implement an access key approach that Emilio says went live. End result is that a Dissolved Oxygen notebook targeted at NERRS stations won't work "out-of-the-box".

## Stand-up for ASA  
#### Accomplishments
* Completed winds obs vs model data [progress report] (https://github.com/ioos/system-test/issues/135) and [notebook] (https://github.com/ioos/system-test/pull/118) (needs to be merged, please)

#### Anticipated activities
* Develop a single "spin-off notebook" for the basic oceanography variables already being tested (wind, waves, currents, water level) to test all end points for multiple geographies. Develop a chart summarizing available endpoints per variable/csw/location.  Idea is to create one nicely organized notebook that tests multiple variations of CSW/location for each variable and avoid the need to create many simple spinoffs.
* Finalize waves extremes notebook
* Model-HFRadar-Obs comparison notebook; coordinate with ASA EDS team about access/use of HFRADAR data
* Update folder structure for Theme 2 (to reduce length)
* Finalize currents extremes notebook
* Update currents model-obs notebook to (1) point out that the easiest datasets to access are not really comparable the Chesapeake Bay example in the map and (2) look for model data inside CB

#### Issues  
* Initial tests of other catalogs (to find wind data) did not yield any results; will investigate further (e.g. for other geographies) before documenting in a progress report
* ASA team has multiple ideas for new notebooks, need to discuss next steps and ensure we're not duplicating effort with others.  Examples include (1) determine whether sea ice is a factor when modeling oil spills (too much overlap with polar bears & ice?); (2) Water temperature - need a scenario simpler than cold pool to start, e.g. Can we discover and access high enough resolution data to support recreational activities (surfing, swim races) or given a fish death event, can we find evidence of hypoxia? More generally, can we compare obs, model, satellite data, etc.; (3) Can we use USGS rapid deploy gages to discover info about overland inundation? 

# Week of 4 August 2014

## Stand-up for ASA  
#### Accomplishments
* Completed Extreme [currents notebook] (https://github.com/ioos/system-test/blob/master/Theme_2_Extreme_Events/Scenario_2A_Coastal_Inundation/Scenario_2A_Extremes_Currents/Scenario_2A_Extreme_Currents.ipynb) and [progress report] (https://github.com/ioos/system-test/issues/110)
* Completed Extreme waves [notebook](https://github.com/ioos/system-test/pull/139)

#### Anticipated activities
* Develop a single "spin-off notebook" for the basic oceanography variables already being tested (wind, waves, currents, water level) to test all end points for multiple geographies. Develop a chart summarizing available endpoints per variable/csw/location. Idea is to create one nicely organized notebook that tests multiple variations of CSW/location for each variable and avoid the need to create many simple spinoffs.
* Model-HFRadar-Obs comparison notebook; coordinate with ASA EDS team about access/use of HFRADAR data
* Update currents model-obs notebook to (1) point out that the easiest datasets to access are not really comparable the Chesapeake Bay example in the map and (2) look for model data inside CB
* Update folder structure for [theme 2](https://github.com/ioos/system-test/issues/136)

#### Issues  
* Large current time series requests cause issues, so using DAP  [#116] (https://github.com/ioos/system-test/issues/116) & [#81] (https://github.com/ioos/system-test/issues/81)  
* NDBC SOS doesn't serve all of its historical wave data [#137] (https://github.com/ioos/system-test/issues/137) 

# Week of 11 August 2014

## Stand-up for Axiom  
#### Accomplishments  
* Add documentation to baseline tests
* Began work developing other baseline tests

#### Anticipated Activities:
* Work on developing additional baseline tests that test the system as a whole, rather than individual components  
* Continue to develop notebooks for nutrients, salinity, dissolved oxygen, and other variables that haven't been tested in other notebooks (Baseline Scenarios 1D and 1E)

#### Issues
* Some discussion occurred over which time units are CF-compliant, which are acceptable for udunits, which can be used by the NetCDF library, and what is actually used by model developers. [Issue #146](https://github.com/ioos/system-test/issues/146).

## Stand-up for ASA  
#### Accomplishments
* Polished Extreme waves [notebook](https://github.com/ioos/system-test/pull/139) using feedback from the 08/08/2014 meeting
* Ben Adams is getting up to speed and reviewing notebooks
* Initiated discussion on implementing testing procedure for notebooks. See issue [#147](https://github.com/ioos/system-test/issues/147)

#### Anticipated Activities:
* Develop a single "spin-off notebook" for the basic oceanography variables already being tested (wind, waves, currents, water level) to test all end points for multiple geographies. Develop a chart summarizing available endpoints per variable/csw/location. Idea is to create one nicely organized notebook that tests multiple variations of CSW/location for each variable and avoid the need to create many simple spinoffs.
* Model-HFRadar-Obs comparison notebook; coordinate with ASA EDS team about access/use of HFRADAR data
* Update currents model-obs notebook to (1) point out that the easiest datasets to access are not really comparable the Chesapeake Bay example in the map and (2) look for model data inside CB
* Update folder structure for [theme 2](https://github.com/ioos/system-test/issues/136)

#### Issues
None