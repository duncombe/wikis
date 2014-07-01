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
* What we've done in the past week  

#### Anticipated activities  
* What we're planning to do in the coming week 

#### Issues  
* Recurring issues that may span a number of individual issues reported in GitHub  


## Stand-up for Axiom  
#### Accomplishments  
* What we've done in the past week  

#### Anticipated activities  
* What we're planning to do in the coming week 

#### Issues  
* Recurring issues that may span a number of individual issues reported in GitHub  

## Stand-up for IOOC  
#### Accomplishments  
* What we've done in the past week  

#### Anticipated activities  
* What we're planning to do in the coming week 

#### Issues  
* Recurring issues that may span a number of individual issues reported in GitHub  