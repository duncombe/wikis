_**Please note: While this page is currently named "Scenario Brainstorming" we've moved away from Scenarios in favor of using Themes and test cases to represent the topical areas we're testing.**_

# Introduction
The entire project is organized into phases or focus areas called themes.  Themes will focus on a large scientific problem area and will be used to identify common problems or needs commonly encountered by  data consumers who work within these theme areas.  Within each theme, the common problems, will be articulated in a problem statement and a script will be developed to attempt to deliver the stated need using the distributed set of tools and data that comprise DMAC.  These theme areas are similar to the GEOSS societal benefit areas.    

The problems or questions, henceforth test case, are intended to be fairly granular and confined statements of need.  They are not intended to introduce a new scientific problem or a new data gathering strategy, but rather are simple examples of how data consumers currently interact with data, or how they wish to in the not too distant future.  A test case is executed in well-defined, sequential steps, following the standard, discover-access-use paradigm.  Each test case begins with a statement of need which is translated into Python query executed against published metadata registries.  Upon completion (successful or not) of the query, the test case continues on to act on the results of the query.  Actions may include, among other things, simple summaries of the query results in tabular form or attempting to access the data described by one or more of the results.  The final result of the test case is a statement of whether or not the original need was met.  Each step in a test case includes criteria to evaluate whether that test step passed, and if not, what effect the failure might have on the overall success of the test case.  See _this yet to be created wiki page_ for a more detailed template describing the test cases and the scripts that embody them.

# Use Cases

The the GEOSS Architecture Implementation Pilot, Phase 3, [Use Case Engineering Report](http://www.ogcnetwork.net/pub/ogcnetwork/GEOSS/AIP3/documents/AIP-3_Use_Cases_ER110210.pdf) provides a set of use cases that are relevant to DMAC and distributed data networks in general but are not science focused.  These so called transverse use cases may be useful in helping us standardize the data we will collect from each test case.  This section is included currently, just as a placeholder for future elaboration/consideration.  It's not clear if included the somewhat dense language of system engineering use case principles will make for a better publication in the end.  Nevertheless there is some useful information in these references.

## Use Case: Search for Resources 
Steps for portals and application clients to support the GEOSS User in searching for resources of interest via Community Catalogs and Registries

## Use Case: Present Services

## Use Case: Exploit Data Visually and Analytically

# Theme 1: Baseline Assessment
The baseline assessment theme will concentrate on use cases that aren't necessarily science focused but instead are focused on a basic assessment of the tools we have to apply to the Discovery/Access/Use paradigm.  Basic statistics on the number of data sets in each chosen registry, the standards advertised, the dialects of the metadata within the registries etc.  


*_Editors note: we will note be testing or deploying any push technologies so Alerts are out of scope for DMAC and for this project._*

## Questions for consideration

* What are the essential elements that dictate whether a search was successful or not?
* List the interfaces that a catalog provides (html page with forms, csw, opensearch, ckan etc)
* For each registry, summarize the contents along several important query parameters 
  * Variable names (IOOS core variables, CF standard names etc)
  * Presence/absence of well defined service interfaces
  * Clear human readable titles/abstracts/summaries
  * Presence/absence of keywords and references to keyword vocabularies (preferably machine readable)
  * 

# Theme 2: Extreme Events 

## Questions for consideration

* Comparison of predicted vs average water levels at a particular location
* Retrospective comparison of modeled water levels from more than one model at a particular location
* In general, any model data comparison problem has relevance here or in the next theme area
* Comparison of like data types from distinct sources (Can we plot USGS water level and CO-OPS water level using the same script?)
* 

# Theme 3:  TBD (Considering Ecosystem, Water Quality, Biology, Climate Change, CMSP)
As a starting point for thinking about energy siting within CMSP as a potential third theme, here's a short [paper](https://drive.google.com/file/d/0B8p4sUXIeKn1WVFhaGo0UzBnWjQ/edit?usp=sharing) emphasizing that the driver behind many state based CMSP has been the siting of energy.

The [InVEST Model for Wind Energy Siting](http://ncp-dev.stanford.edu/~dataportal/invest-releases/documentation/current_release/wind_energy.html#required-inputs) might be a good place to gather required data sets (See, "Required input" section in the link).  Looking through, however, I might argue that it could be additionally useful to add data sets required for permitting (e.g. migratory birds, marine mammals, fish abundance/species).

## Questions for consideration

# Scenarios for consideration in the integrated DATE and Systems Integration Test activities (DMAC-ST Input)

Insert raw material from https://docs.google.com/a/noaa.gov/document/d/1veNhCt8Tk_0kedMXnHPWBj9SOcJ8y4zwXPBIdnQ1NFs/edit#heading=h.vzggr24i8e93