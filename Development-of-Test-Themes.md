# Introduction
The entire project is organized into phases or focus areas called themes.  Themes will focus on a large problem area and will be used to identify common problems or needs commonly encountered by  data consumers who work within these theme areas.  These theme areas are similar to the GEOSS societal benefit areas.  

Within each theme there is a top level problem statement, which contains the overall objective of the theme.  Themes will be accompanied by Ipython Notebooks which address particular aspects of each theme (e.g. is data from multiple models interoperable? is it possible map physical and biological data sets? are the data sets needed to address a available/integrated into particular data catalogues?).  

Ipython notebooks will be standardized using the following format:

*  **Theme Title**
    *  _**Question**_
               *  A question and summary statement of objectives, which include general success criteria.
         *  DISCOVERY Process (code and narrative)
         *  ACCESS Process (code and narrative)
         *  USE Process (code and narrative)
    *  _**Conclusions**_ (narrative)
         
The procedures will employ iPython scripts that interrogate DMAC registries and repositories, and analyze the returned data against expected results.  From a systems testing perspective, the Question To Be Answered roughly correspond to Test Cases.  However, there is not necessarily a one-to one correspondence between a Question To Be Answered and a test procedure.  Each question may correspond to a number of notebooks in order to increase readibility and modularity of the IPython notebook tools.   

**Nota Bene**: 

1. The Questions To Be Answered are not intended to introduce a new scientific problem or a new data gathering strategy, but rather are examples of how users commonly interact with data.  Alternate procedural flows may be used to address less common or anticipated ways that users interact with DMAC.  

2. Each test case is executed in sequential steps, following a baseline flow of discovery-access-use.  Each test case begins with a summary statement of objectives, which include general success criteria.  Each step of the test case procedure includes evaluation criteria that determine whether that particular step has been successfully executed.  

3. Depending on the importance of a particular test step to the overall test case, the failure of that step may result in failure of the entire test case, or it may result in only partial success.  

4. The core of each  test case is the use of one or more Python queries executed against published metadata registries. The procedure includes evaluation of the results returned by each Python query.  The evaluation may be performed within the Python scripts during execution, or it may be performed manually by the tester.  

5. **Criteria**:  Each step in a test case includes criteria to evaluate whether that test step passed, and if not, what effect the failure might have on the overall success of the test case. 
*  In addition to one or more evaluation criteria for each procedural step, a test case has one or more summary evaluation criteria.  These summary criteria evaluate the degree to which test case results successfully address the appropriate Questions To Be Answered.   

See **Below** for a more detailed templates describing the Themes.

# Theme 1: Baseline Assessment
The baseline assessment theme includes test cases that, as the name of theme states, assess the basic functionality of the Data Management and Communications system. While the test cases for this theme have no slant towards a particular scientific endeavor, the functionality to be tested underlies all subsequent test themes.  To put it simply, the Baseline Assessment theme tests whether registries, catalogs, metadata sets and data sets that are known to meet IOOS certification can be discovered, accessed and used. Results include information such as basic statistics on the number of data sets in each chosen registry, the standards advertised, and the dialects of the metadata within the registries. Information obtained through the use of iPython scripts will be compared against corresponding information retained by a registry, catalog, or data repository owner to answer the question below.


*_Editors note: we will note be testing or deploying any push technologies so Alerts are out of scope for DMAC and for this project._*

## Questions/Topics for consideration

* Discovery, Access, Use protocol/narratives
* What are the essential elements that dictate whether a search was successful or not?
* List the interfaces that a catalog provides (html page with forms, csw, opensearch, ckan etc)
* For each registry, summarize the contents along several important query parameters 
  * Variable names (IOOS core variables, CF standard names etc)
  * Presence/absence of well defined service interfaces
  * Clear human readable titles/abstracts/summaries
  * Presence/absence of keywords and references to keyword vocabularies (preferably machine readable)

NOTE: See github.com/osgeo/Cat-Interop for a project that should be included as a contribution to the system-test.  Standardizing vocabulary of service type descriptions for CS/W 2.0.2 implementations.



# Theme 2: Extreme Events 
The Extreme Events theme, as its name suggests, focuses on the analysis of data related to events that produce extreme adverse effects in a geographic area.  Possible topics within this heme may include, but not be limited to, the following.

## Severe Coastal Storm
 As a severe storm is approaching the coast, forecast models are continually being revised as new information about storm’s offshore position and intensity becomes available.   
* How accurate are these models results compared to the measured waves, river flows and water levels?   
* After the storm abates, inundation data should help inform where should responders go to help with the most affected areas.  
* And much after the storm, comparing recorded data values to predicted data values assists in identifying shortcomings of the model and can suggest ways for improving a model's predictive power.

### Questions to Guide Corresponding IPython Notebooks

* Can we discover, access and compare modeled water levels by accessing a CSW (See, [Service Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs) for all available water level models and then overlaying the output for an example bounding box and time period? 
* Can we discover, access, and compare modeled water levels against observed water levels within a particular bounding box? 
* Can we discover, access, and compare water level data from different agencies and overlay that data for a particular geographic bounding box (e.g. USGS and CO-OPS) within a single IPython notebook? 
* Can we discover, access, and overlay data from federal catalogs on water level with local data sources?
* Can we discover, access, and overlay data from flood models accessible through federal data catalogues with coastal elevation data and baythmetric data in a single IPython notebook?

#### Required data to answer the questions (Source for each type of data identified in parentheses):

- data available on this custom USGS Sandy Mapper app: [Need to name the app]
- Rapid deployment tide gauges(USGS)
- Rapid deployment stream gauges (USGS)
- Wave heights sensors (NOAA, IOOS regions)
- Barometric Pressure data(NOAA NOS, NOAA NWS)
- Wind data (NOAA, IOOS Regions)
- Long-term tide gauges (USGS, NOAA, USACE)
- High-water marks (USGS, NOAA, FEMA)
- Models from USACE, NOAA, IOOS Regions
- NOAA NHC: SLOSH
- NOAA NOS: ASGS, 
- NERACOOS Regional Resources Identified:
    *  [NOAA Tides Online](http://tidesonline.nos.noaa.gov/plotcomp.shtml?station_info=8410140+-+Eastport,%20ME&type=Tide+Data)
    *  [CMS Storm warning system](http://hudson.dl.stevens-tech.edu/SSWS/)
    *  [Delaware Coastal Flood Monitoring System](http://www.coastal-flood.udel.edu/)
    *  [NERACOOS coastal flooding and erosion tool](http://www.neracoos.org/dataproducts/forecast/coastal_flooding_forecast/portland)
    *  [NERACOOS Water Level Display](http://p5.neracoos.org/products/modeldata/popup.html?page=popup&platform=hampton&model_type=NEC)
    *  [NERACOOS water level obs/model viewer](http://www.neracoos.org/datatools/forecast/modelobs)

### ADDITIONAL EXTREME EVENTS THEMES:
## Physical and Biological Disaster
Physical disasters often impact entire ecosystems and mitigation efforts can be improved by integrating physical data about conditions and the disaster itself with information on the impacted species of interest.

###Example: Oil Tanker Spill
An oil tanker loaded has collided with another vessel 5 nautical miles SE of the entrance to Delaware Bay.  A large quantity of oil has been released into the marine environment, threatening the shoreline of a particular coastline. 

#### Questions to Guide Corresponding IPython Notebooks
* Can we discover, access and map high resolution coastline and velocity vectors from a real time data set accessible through CSWs and then map modeled water velocity vectors at a point in the future from the designated time of the test in the same geographic area? 
* Can we discover, access and map bathymetry, tidal data, currents, winds, and overlay that with data reflecting coastal ecological vulnerabilities in a designated bounding box for a designated time in single IPython notebook? 
* Can we discover, access and map satellite remote sensing images in real time against real time and future model projection data of velocity vectors in a single IPython notebook?
* Can we discover, access and map high resolution coastline, velocity vectors, and data on the [core IOOS biological variables](http://www.iooc.us/activities/biological-integration-observation-task-team/)? 
* Can we discover, access and map an oil spill trajectory using GNOME for a particular location?  
    *  Answering this question will also mean answerign the question of whether we can discover, access and use wind speed data and river flow rates data in a single script and then call the GNOME model to run the scenario after entering a specified spill size, location, pollutant type, model duration, and uncertainty (See, [GNOME Example Problem Document](http://response.restoration.noaa.gov/sites/default/files/Gnome_NSlope_Ex.pdf)). 

####Required Data to Answer Questions
* weather 
* satellite remote sensing images
* wind speed/direction
* surface currents
* threatened and endangered species data
* shoreline types 
* river flow data
* high resolution coastline data
* bathymetry 
* boundaries (vessel traffic, shipping lanes, state/territorial waters boundaries) 
* [IOOS Core Biological Variables](http://www.iooc.us/activities/biological-integration-observation-task-team/)
* RESOURCES Consulted:
    *  [Maritime Environmental Emergency Oil Spill Trajectory Model](http://www.amsa.gov.au/environment/maritime-environmental-emergencies/national-plan/General-Information/OSTM/faq/answers.asp)
    *  [NASA Imagery of Oil Spills](http://www.nasa.gov/topics/earth/features/oilspill/index.html)
    *  [NOAA Ocean Service Oil Spill Trajectory Model](http://oceanservice.noaa.gov/education/stories/oilymess/supp_trajmodel.html)
    *  [General NOAA Operational Modeling Environment](http://response.restoration.noaa.gov/gnome)

## Search & Rescue 
Many disaster responses requiring rescue can be improved by greater knowledge about the physical/chemical/biological conditions.

###Example: Commercial Aircraft Crash
A large commercial aircraft en route LAX from Honolulu with several hundred passengers onboard has crashed into the Pacific Ocean midway between the Hawaiian Islands and the California coast.  A massive search and rescue effort is underway. 

####Questions  To Be Answered
* Where exactly is the crash site?
* Where will survivors be lost likely to be found?
* Where will floating wreckage be found?
* How deep is the ocean bottom at the crash site?
* Are there weather conditions that might assist or hamper the search & recovery effort?
* How will current and forecast weather conditions near the crash area affect the survivors?

####Required Data to Answer Questions
* GPS location of crash site
* real-time weather 
* ocean circulation observations 
* real-time precipitation 
* cloud cover 
* wind speed/direction 
* surface currents
* wave heights
* sea surface temperature
* forecast wind speed/direction
* forecast surface currents
* forecast weather

## Invasive Species
One of the major problems that resource managers face is invasive species. Improved physical and biological data can help resource managers improve and refine the strategies they develop in order to mitigate the impacts of invasive species on valued resources (e.g. recreational areas, commercial species, etc.).  

###Example: Asian Tiger Shrimp  
Asian Tiger Shrimp, an aquaculture species, has invaded the southern US (NC-TX).  Very few occur in areas adjacent to Texas.  Hypotheses about their introduction to US waters include:
* Ballast transport from their native range in the Pacific;
* Ballast or current transport from introduced populations off West Africa;
* Ballast or current transport from introduced populations in northern South America;
* Current transport from the Caribbean from escapes from aquaculture ponds there.

####Questions for Consideration
The species is still expanding its range.  Pick an origin from above, or that a hurricane flooded an aquaculture facility on the Gulf Coast.  Potential scenario and questions:
* What is predicted distribution and spread? 
* Where should we look for breeding areas?
* Why don't they occur in Texas?  
* Can you tell where they came from based on spread? 
* Will they overlap with other shrimp species - in distribution and/or diet? 

####Required Data to Answer Questions
* *currents 
* temperature 
* habitat preferences 
* larval drift
* breeding requirements
* salinity
* habitat preferences    
* native species distributions
* diets of all species      
* frequency of occurrence 
 

# Theme 3:   Marine Energy Planning
The driver behind many state based marine conflict resolution programs has been the siting of energy projects. The [InVEST Model for Wind Energy Siting](http://ncp-dev.stanford.edu/~dataportal/invest-releases/documentation/current_release/wind_energy.html#required-inputs) is a good starting place for required data sets (See, "Required input" section in the link).  Additional data sets required for permitting coastal energy projects may include those related to migratory birds, marine mammals, and fish abundance/species).  Possible topics within this area include those listed below.

## Location of Wind Turbine Farm
A state is is the process of delimiting an area off its coast that is suitable for the placement of a major wind turbine farm.  The state must adhere to a number of laws and implementing policies before it can formally delineate an area for wind turbine development and solicit bids.

### Questions for consideration
* What data is needed for particular energy planning policies (Outer Continental Shelf Lands Act, National Environmental Policy Act, etc)?
* Can that data be easily accessed from the available registries and catalogs?  If so, which registries can each data set be accessed through?  
* Using baseline metrics developed under Theme 1 for registries, are there certain registries that are better or worse for accessing particular data sets?

### Required Data to Answer Questions
* wind data point
* area of interest
* bathymetry
* land polygon for distance calculations
* global wind energy parameters
* turbine type
* minimum depth for offshore wind farm installation
* maximum depth for offshore wind farm installation
* minimum distance for offshore wind farm installation
* maximum distance for offshore wind farm installation

## Mineral Extraction
The Department of Interior Bureau of Ocean Energy Management is considering opening several tracts in the Gulf of Mexico for petroleum exploration. As part of their due diligence under regulations implementing the Outer Continental Shelf Lands Act, the Bureau must prepare an environmental impact statement before opening the tract to bids. The environmental impact statement must consider the potential impact of exploration and drilling on area fisheries.

### Questions TO Be Answered
*  What are the trends in phytoplankton health in the area over the past 30 years?
*  What are the metrics for zooplankton health in the area over the past 30 years?
*  What are the metrics for commercial fish species in the area over the past 30 years?
*  Are there analog areas that have undergone exploration and drilling that can be used for comparison?
*  If so, what trends can be observed in the metrics for phytoplankton, zooplankton and commercial fish species in the analog areas?

### Data Required to Answer Questions
* area of interest
* bathymetry
* phytoplankton survey results
* zooplankton survey results
* water quality metrics


# RESOURCES AND REFERENCES FOR TESTING APPROACH

# Source for Test Cases

The the GEOSS Architecture Implementation Pilot, Phase 3, [Use Case Engineering Report](http://www.ogcnetwork.net/pub/ogcnetwork/GEOSS/AIP3/documents/AIP-3_Use_Cases_ER110210.pdf) provides a set of use cases that are relevant to DMAC and distributed data networks in general but are not science focused.   They may be useful as templates for building procedures for various DMAC test cases.  These so called transverse use cases may be useful in helping us standardize the data we will collect from each test case. [Note that the term "transverse use case' is not defined in systems testing literature and seems to be particular to the GEOSS Architecture Implementation Pilot project.]   This section is included currently, just as a placeholder for future elaboration/consideration.  It's not clear if included the somewhat dense language of system engineering use case principles will make for a better publication in the end.  Nevertheless there is some useful information in these references.  The structure and style of the GEOSS use cases should not be lifted ans used without revision in DMAC testing. Rather, the GEOSS use cases can suggest procedures that can be easily adapted to test DMAC functionality.  Of particular interest to DMAC are three GEOSS general use cases:

* Search for Resources
* Present Services
* Exploit Data Visually and Analytically