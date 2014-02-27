# Introduction
The entire project is organized into phases or focus areas called themes.  Themes will focus on a large scientific problem area and will be used to identify common problems or needs commonly encountered by  data consumers who work within these theme areas.  These theme areas are similar to the GEOSS societal benefit areas.  Within each theme there is a top level problem statement, which contains the overall objective of the theme.  The problem theme and its objectives are articulated in one or more are one or more Questions To Be Answered.  One or more step-by-step procedures will use DMAC resources to answer the Questions.  The procedures will employ iPython scripts that interrogate DMAC registries and repositories, and analyze the returned data against expected results.

From a systems testing perspective, the Question To Be Answered roughly correspond to Test Cases.  However, there is not necessarily a one-to one correspondence between a Question To Be Answered and a test procedure.  A single test procedure may address more than one Question To Be Answered.  Conversely, a test procedure may not completely satisfy any Question To Be Answered.  The Questions To Be Answered are not intended to introduce a new scientific problem or a new data gathering strategy, but rather are examples of how users commonly interact with data.  Alternate procedural flows may be used to address less common or anticipated ways that users interact with DMAC.  

Each test case is executed in sequential steps, following a baseline flow of discover-access-use.  Each test case begins with a summary statement of objectives, which include general success criteria.  Each step of the test case procedure includes evaluation criteria that determine whether that particular step has been successfully executed.  Depending on the importance of a particular test step to the overall test case, the failure of that step may result in failure of the entire test case, or it may result in only partial success.  The core of each  test case is the use of one or more Python queries executed against published metadata registries. The procedure includes evaluation of the results returned by each Python query.  The evaluation may be performed within the Python scripts during execution, or it may be performed manually by the tester.  Each step in a test case includes criteria to evaluate whether that test step passed, and if not, what effect the failure might have on the overall success of the test case. In addition to one or more evaluation criteria for each procedural step, a test case has one or more summary evaluation criteria.  These summary criteria evaluate the degree to which test case results successfully address the appropriate Questions To Be Answered.   See _this yet to be created wiki page_ for a more detailed template describing the test cases and the scripts that embody them.

# Source for Test Cases

The the GEOSS Architecture Implementation Pilot, Phase 3, [Use Case Engineering Report](http://www.ogcnetwork.net/pub/ogcnetwork/GEOSS/AIP3/documents/AIP-3_Use_Cases_ER110210.pdf) provides a set of use cases that are relevant to DMAC and distributed data networks in general but are not science focused.   They may be useful as templates for building procedures for various DMAC test cases.  These so called transverse use cases may be useful in helping us standardize the data we will collect from each test case. [Note that the term "transverse use case' is not defined in systems testing literature and seems to be particular to the GEOSS Architecture Implementation Pilot project.]   This section is included currently, just as a placeholder for future elaboration/consideration.  It's not clear if included the somewhat dense language of system engineering use case principles will make for a better publication in the end.  Nevertheless there is some useful information in these references.  The structure and style of the GEOSS use cases should not be lifted ans used without revision in DMAC testing. Rather, the GEOSS use cases can suggest procedures that can be easily adapted to test DMAC functionality.  Of particular interest to DMAC are three GEOSS general use cases:

* Search for Resources
* Present Services
* Exploit Data Visually and Analytically

# Theme 1: Baseline Assessment
The baseline assessment theme includes test cases that, as the name of theme states, assess the basic functionality of the Data Management and Communications system. While the test cases for this theme have no slant towards a particular scientific endeavor, the functionality to be tested underlies all subsequent test themes.  To put it simply, the Baseline Assessment theme tests whether registries, catalogs, metadata sets and data sets that are known to meet IOOS certification can be discovered, accessed and used. Results include information such as basic statistics on the number of data sets in each chosen registry, the standards advertised, and the dialects of the metadata within the registries. Information obtained through the use of iPython scripts will be compared against corresponding information retained by a registry, catalog, or data repository owner to answer the question below.


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

# Theme 2: Weather and Climate-Related Extreme Events 

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
##A. Physically Focused Extreme Events

###Rationale:

•	As a severe storm is approaching the coast, forecast models are continually being revised as new information about storm’s offshore position and intensity becomes available.   
•	How accurate are these models results compared to the measured waves, river flows and water levels?   
•	After the storm abates, inundation data should help inform where should responders go to help with the most affected areas.  
•	And much after the storm, comparing recorded data values to predicted data values assists in identifying shortcomings of the model and can suggest ways for improving a model's predictive power.

###Required data to satisfy scenario (Source for each type of data identified in parentheses):

- data available on this custom USGS Sandy Mapper app: [Need to name the app]
- Rapid deployment tide gauges(USGS)
- Rapid deployment stream gauges (USGS)
- Wave heights sensors (NOAA, IOOS regions)
- Barometric Pressure data(NOAA NOS, NOAA NWS)
- Winddata (NOAA, IOOS Regions)
- Long-term tide gauges (USGS, NOAA, USACE)
- High-water marks (USGS, NOAA, FEMA)
- Models from USACE, NOAA, IOOS Regions
- NOAA NHC: SLOSH
- NOAA NOS: ASGS, 

##B. Biologically Focused Extreme Events:  These items should be relocated to the Marine Ecosystem Theme
##1. Invasive Species

###Rationale:

•	One of the major problems that resource managers face is invasive species.  
•	Improved physical and biological data can help resource managers improve and refine the strategies they develop in order to mitigate the impacts of invasive species on valued resources (e.g. recreational areas, commercial species, etc.).  

Example A: Asian Tiger Shrimp, an aquaculture species, has invaded the southern US (NC-TX).  Very few occur in areas adjacent to Texas.  We don’t know their origin:
·         ballast transport from their native range in the Pacific;
·         ballast or current transport from introduced populations off West Africa;
·         ballast or current transport from introduced populations in northern South America;
·         current transport from the Caribbean from escapes from aquaculture ponds there.
·         Where they breed
 
Example A: Required data to satisfy scenario:

The species is still expanding its range.  Pick an origin from above, or that a hurricane flooded an aquaculture facility on the Gulf Coast.  Potential scenario and questions:
·         What is predicted distribution and spread? 
•	currents 
•	temperature 
•	habitat preferences 
•	larval drift
·         Where should we look for breeding areas? 
•	breeding requirements
•	salinity
•	habitat preferences
•	marshes (spatial extent, type)
·         Will they overlap with other shrimp species - in distribution and/or diet? 
•	native species distributions
•	diets of all species
·         Why don't they occur in Texas?  
•	benthic fauna?
•	bottom structure?
•	Competitors
•	occurrence  
•	currents
·         Can you tell where they came from based on spread?  
•	currents
 
Example B: Nile Tilapia, an aquaculture species from Africa, is widely farmed around the world.  It has escaped and established virtually everywhere it has been grown.  They are known primarily from freshwater areas.  In fact there is a population upstream on the Escatawpa River, MS, at a power plant.  
 
In 2005 when Hurricane Katrina hit the Gulf Coast, an aquaculture facility on the Mississippi coast, adjacent to the marsh, was flooded and lost all its stock.

Example B: Required data to satisfy scenario:

·         Will they survive in the marsh? 
•	salinity tolerance 
•	temperature tolerance
•	marsh temperatures
•	habitat
•	food 
·         Can they survive the salinity long enough to migrate to a nearby freshwater river?  
•	salinity levels post storm and variation
•	distances to suitable rivers
·         If they can survive, can they reproduce? What is their potential distribution?  
•	Temperature
•	salinity 
•	river distances
•	tolerances
##C. Physical and Biological
###Rationale: 
•	Physical disasters often impact entire ecosystems and mitigation efforts can be improved by integrating physical data about conditions and the disaster itself with information on the impacted species of interest.

Example A: Oil Tanker Spill
An oil tanker loaded has collided with another vessel 5 nautical miles SE of the entrance to Delaware Bay.  A large quantity of oil has been released into the marine environment, threatening the shoreline of the Delmarva Peninsula, Delaware Bay, and the New Jersey coast. 

Example A: Required data to satisfy scenario:
•	weather 
•	sea surface temperature 
•	data required for oil spill trajectory models
•	real-time precipitation
•	cloud cover
•	wind speed/direction
•	surface currents
•	wave heights, 
•	threatened and endangered species data
•	shoreline types 
•	 waterway use data 
•	boundaries (vessel traffic, shipping lanes, state/territorial waters boundaries) 

Example B: Arctic Oil Spill  

With the increased interest in Arctic drilling and reduced sea ice enabling more ship transportation in the Arctic, the risk of an oil spill is increasing.  

Example B: Required data to satisfy scenario:
•	real-time and historic baseline data on wind speed/direction
•	ocean currents
•	chemical and nutrient distributions
•	macro- and microfauna distributions
•	habitat characterization (including bathymetry)
•	ocean temperature and salinity 
•	regional climatologies
•	waves
•	modeled circulation
Example C: Assessing the injuries to pelagic tunas in the gulf of Mexico

Atlantic Bluefin tuna (Thunnus thynnus) are among the world’s more imperiled commercial pelagic fish. The shelf waters of the Gulf of Mexico are the known North American spawning ground for a portion of the Atlantic western Atlantic stock. The Deepwater Horizon Oil Spill occurred during the peak of the known spawning time, thereby exposing fish at all life stages from egg to adult.

Example C: Required data to satisfy scenario:
•	bluefin tagging/telemetry data
•	bluefin tracks
•	oil spill tracks
•	historical bluefin tagging data
•	waves
•	modeled circulation
##D. Rescue Scenarios

###Rationale:
•	Many disaster responses requiring rescue can be improved by greater knowledge about the physical/chemical/biological conditions.

Example A: Commercial Aircraft Crash

•	A large commercial aircraft en route LAX from Honolulu with several hundred passengers onboard has crashed into the Pacific Ocean midway between the Hawaiian Islands and the California coast.  A massive search and rescue effort is underway.  

Example A: Required data to satisfy scenario:
•	real-time weather 
•	ocean circulation observations 
•	real-time precipitation 
•	cloud cover 
•	wind speed/direction 
•	surface currents
•	wave heights
•	sea surface temperature
 
Example B: Search and Rescue (SAR)

•	Around 5PM on an overcast day during the Hurricane season, a twin engine plane on a routine flight over the Atlantic Ocean about 200 miles off the US shore runs into catastrophic engine problems and the captain decides to make an immediate water landing. Emergency procedures work per plan and the plane ‘lands’ safely. All 150 passengers are evacuated on rafts and the rafts are detached from the plane after the captain and crew notice smoke billowing from one of the engines. The plane and rafts begin to drift independently.
•	Complicating the situation, radio contact is lost between the crew and on-shore authorities shortly after the plane water landed, on-shore authorities to rely entirely on prediction to determine the location of the rafts and the plane in the ensuring hours so that a comprehensive search and rescue effort, including the critical dispatching of all required air and marine assets – including non-governmental ones - can be initiated. Authorities recognize that they have only limited time on hand before the rafts run out of life-supporting supplies, and before it gets to be night time.

Example B: Required data to satisfy scenario:

•	 real-time weather 
•	ocean circulation observations 
•	real-time precipitation 
•	cloud cover 
•	wind speed/direction 
•	surface currents
•	wave heights
•	sea surface temperature.

##New Research Questions that May not be Appropriate for this Project(?)
###Annual Catch Limits for Reef fishes

Reef fish population in the Hawaiian Archipelago was overfished and the Scientists/managers from Western Pacific Regional Fisheries Management Council need to estimate the Annual Catch Limits for reef fishes to develop fisheries management plans for reef fishes as defined by the Magnuson-Stevens Fishery Conservation and Management Reauthorization Act (MSRA).
 
Potential scenario and questions:
1)      Annual catch limits for some reef fishes
Data to use includes reef fish species and abundance data collected in NOAA Towed Diver Surveys.
 
Places to look for this data: IOOS Catalog or PacIOOS ERDDAP server or NOAA GEO-IDE ERDDAP.
 
###Fishing for Hurricanes

Every day, Shay, a professor of meteorology and physical oceanography, was plotting the depth and location of the 26° C isotherm—a zone of warm water equal to 78.8° F—on his website. Meteorologists find the data useful, since hurricanes are known to intensify after passing over pockets of warm water in the ocean. The deeper the warm water goes, the more intense a storm becomes. The problem with Shay’s satellite model was that it had trouble defining the boundaries of the isotherm. This kind of data can be obtained by gliders. But, in the strong currents off the Gulf Coast,  gliders may be less effective. “The Gulf current moves at around 6 or 7 miles per hour, whereas gliders move at about half a knot, or .6 miles per hour”.  Animals like Tarpon, on the other hand, travel at sustained speeds of 35 miles per hour. They can go up to 50. They’re not going to get washed out to sea by the Gulf Stream.  

Jerry Ault Rosenstiel School recently discovered that tarpon adhere to the 26° C isotherm during their annual migration through the Gulf of Mexico and the Caribbean Sea.
By using Ault’s fish to gather temperature and depth data about the 26° C isotherm, they could essentially fill in the gaps of Shay’s satellite model. The fish, in other words, could help meteorologists make more accurate hurricane forecasts.

Potential scenario questions:
Shay’s satellite model can be improved with data from Jerry’s tagged Tarpon?
Potential location of this data: IOOS catalog, SECOORA ERDDAP.

###Fishing for eddies

Frank Bub ocean modeler at NAVOCEAN is looking to augment observations into NAVO’s global (HYCOM) and region (NCOM) models.  He noticed that most eddies and frontal zones are not well observed with existing observing systems (buoys, gliders).  Dan Costa and his team at TOPP are continuously gathering data on eddies and frontal zones using animal like elephant seals in the coast of California.  Dan recently deployed 20 CTD tags on elephant seals and ready to provide this data to Frank.  Potential scenario questions:  Observations from CTD tags on elephant seals would augment the accuracy of HYCOM models?  Where to fish for tagged data? IOOS catalog, NOAA ERDDAP, ATN DAC ?
 
###Survival of Columbia River Salmon Stocks

Many Columbia River salmon stocks are listed as threatened or endangered, a result often attributed to the construction and operation of the Columbia River dams. Though, the mortality of salmon smolts during their migration out of freshwater and into the ocean has been difficult to measure. In the Columbia River, which has an extensive network of hydroelectric dams, the decline in abundance of adult salmon returning from the ocean since the late 1970s has been ascribed in large measure to the presence of the dams, although the completion of the hydropower system occurred at the same time as large-scale shifts in ocean climate, as measured by climate indices such as the Pacific Decadal Oscillation.
 
Recently the survival of salmon smolts during their migration to sea was measured using elements of the large-scale acoustic telemetry system, the Pacific Ocean Shelf Tracking (POST) array that is now under global OTN.
 
Potential scenario and questions:
 
1)  	the decrease of salmon survival is caused by extensive network of hydroelectric dams  or
2)  	factors other than dams play a larger, unsuspected role in salmon survival.
 
Users: Agency scientists and managers
Data to target to answer these questions: NANOOS POST/OTN Animal Acoustic Telemetry data.
Place to look for the data: IOOS Catalog, NANOOS ERDDAP and GEOSERVER.

[Raw Material from DMAC Steering Team Brainstorming] (https://docs.google.com/a/noaa.gov/document/d/1veNhCt8Tk_0kedMXnHPWBj9SOcJ8y4zwXPBIdnQ1NFs/edit#heading=h.vzggr24i8e93)