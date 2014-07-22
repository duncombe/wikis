 
[Introduction](#intro)  
[Theme 1: Baseline Assessment](#theme1)  [The Elusive Theme.  Is it dead, alive or both?]
* [Scenario 1A: Model Strings](#scenario1A)
* [Scenario 1B: Core Variable Strings](#scenario1B)
* [Scenario 1C: WebService Strings](#scenario1C)

[Theme 2: Extreme Events](#theme2)   
* [Scenario 2A: Coastal Inundation](#scenario2A) [Under development.  Nearing completion]
* [Scenario 2B: Coastal Flooding Information](#scenario2B) [Should it be developed? Probably not.]
* [Scenario 2C:  Oil Spill Response Modeling](#scenario2C) [Used to be Oil Tanker Spill.  Can be used by Axiom to apply to oil exploration in the Chukchi Sea.  Much information available from Deepwater Horizon, Exxon Valdez, Cosco Busan S.F. Bay Incident]
* [Scenario 2D:  Search & Rescue] (#scenario2D)  [Stop searching.  This scenario is beyond rescue]
    
[Theme 3: Species Protection & Marine Habitat Conservation](#theme3)  
*  [Scenario 3A:  Identifying Factors Affecting Species Viability(#scenario3A) [ Used to be Assessing Bering Seabird Vulnerability. Much of the code for Seabird Vulnerability can be repurposed for other species in other areas]
*  [Scenario 3B:  Assessing the Atlantic Continental Shelf Cold Pool](#scenario3B) [Are there any data for this one? Not feasible within project schedule]
*  [Scenario 3C:  Deep Blue Water Use Case Scenario](#scenario3C) [Not feasible within project schedule]
*  [Scenario 3D:  Assessing Chesapeake Bay Biology] (#scenario3D) [This might be a candidate for another application of Identifying Factors Affecting Species Viability.]
*  [Scenario 3E:  Assessing the Quality of Baleen Whale Summer Feeding Grounds Off the New England Coast](#scenario3E) [Put a harpoon in this one and leave it to Captain Ahab]
*  [Scenario 3F:  Planning for Wind Turbine Sites using Ecosystem Base Approach](#scenario3F) [Is this feasible within current schedule?]
*  [Scenario 3G: Mineral Extraction](#scenario3G) [Is this feasible within current schedule?]
*  [Scenario 3H: Exploring environmental changes affecting Polar Bears](#scenario3H) [As of July 11, Derrick to provide registry information to Kyle, who will finish the associated Notebooks.  Kyle estimates 8 hours of development time]
<a name="intro"/>

# Introduction

The strategy for DMAC integration testing is to package discrete test cases and their scripts within larger contexts called themes.  Each theme provides one or more scenarios that generates specific questions that require discovery, access and use of appropriate metadata and data.  The themes provide a realistic framework within which to frame and and address public policy questions with IOOS data.

Within each theme there is a top level problem statement, which contains the overall objective of the theme.  For a theme with more than more objective, two or more scenarios will address particular objectives within the theme.  Themes will be accompanied by IPython Notebooks which address particular questions under each theme.  Each IPython notebook will include comments that identify the theme for which the notebook is used, the question areas that the notebook addresses, the results from executing the python scripts, and the conclusions that can be drawn from the results.  A particular IPython notebook may address questions of discovery, questions of access and questions of use.

IPython notebooks will be standardized using the following format:

*  **Theme Title**
   * **Scenario Description and Title**
       *  _**Questions**_
         *  DISCOVERY Process (code and narrative)
         *  ACCESS Process (code and narrative)
         *  USE Process (code and narrative)
    *  _**Results and Conclusions**_ (narrative)
         
The procedures will employ IPython scripts that interrogate DMAC registries and repositories, and analyze the returned data against expected results.  There is not necessarily a one-to one correspondence between a Question and a notebook product.  Each question may correspond to a number of notebooks in order to increase readability and modularity of the IPython notebook tools.   

<a name="theme1"/>
# Theme 1: Baseline Assessment
This is the elusive theme.  The logic and approaches used in this theme are inherent within all subsequent themes, and the techniques used for discovery, access and use are common to most, if not all scenarios.  This theme needs a very simple operational definition:

> Researcher Jane Doe is new to IOOS, and wants to find out what information is available for further research.  She decides to cast a broad net over all the IOOS registries to find out 
* how much time series information is available on several common, core oceanographic variables:
** wind speed and direction
** wave height and duration
** water temperature as measured at different depths
** water salinity as measured at different depths
** the direction and speed of any current
* where this information resides, and 
* whether this information can be used as input to a few of the most common data models.< 

The baseline assessment theme includes test cases that, as the name of theme states, assess the basic functionality of the Data Management and Communications system.  While the test cases for this theme have no slant towards a particular scientific endeavor, the functionality to be tested underlies all subsequent test themes.  These test cases will incorporate multiple IOOS Regions and partners, cover a large geographic scope, employ multiple types of data, and cross scientific disciplines.   Results from this baseline assessment will include:
* Basic statistics on the number and type of data sets in each chosen registry or catalog
* The metadata standards and dialects employed within those registries
* A determination if the amount of metadata is sufficient to use the data correctly
* Statistics on the number of types of service protocols/endpoints to access the data
* For a given area of interest list the total number of variables/data sets available in each catalog; list the variables.

Information obtained through the use of IPython scripts will be compared against corresponding information retained by registry, catalog, or data repository owners to evaluate the success of the tests.

Baseline Python notebooks can be found [here.](http://nbviewer.ipython.org/github/ioos/system-test/tree/master/Theme_1_Baseline/)


### Questions to Guide Corresponding IPython Notebooks

* Discovery, Access, Use protocol/narratives
* What are the essential elements that dictate whether a search was successful or not?
* List the interfaces that a catalog provides (html page with forms, csw, opensearch, ckan etc)
* For each registry, summarize the contents along several important query parameters 
  * Variable names (IOOS core variables, CF standard names etc)
  * Presence/absence of well defined service interfaces
  * Clear human-readable titles/abstracts/summaries/identifiers contained in the metadata
  * Presence/absence of keywords and references to standardized keyword vocabularies (preferably machine readable)

NOTE: See github.com/osgeo/Cat-Interop for a project that should be included as a contribution to the system-test.  Standardizing vocabulary of service type descriptions for CS/W 2.0.2 implementations.

<a name="scenario1A"/>
* Scenario 1A: Model Strings
Guiding Question: Can we pull out model records from CSW endpoints based on a series of model strings?  And, based on this exercise, is there a need for standardized model strings in order to ensure the discoverability of these records?

Methodology
*  Strings searched for in endpoints: model_strings = ['roms','selfe','adcirc','ncom','hycom','fvcom']
*  Notebook provides a data frame with listed endpoints, records, titles of records, and title lengths.

<a name="scenario1A"/>
* [Scenario 1B: Core Variable Strings]
Guiding Question: Using a list of Core IOOS Variables and the SPARQLWrapper vocabulary mapping tool, can we search and quantify records from CSW endpoints that relate to core variables?

Methodology
*  Strings searched for in endpoints: var_key = ['fish','phytoplankton','zooplankton']
*  Notebook provides code that utilizes SPARQLWrapper tool
*  Notebook provides output in the form of a dataframe listing endpoints searched, records, record titles, and length of records.
*  Unresolved Question: The use of SPARQLWrapper does not seem to enhance the search terms based on Core IOOS variables.  

<a name="scenario1A"/>
* [Scenario 1C: WebService Strings]
Guiding Question: Based on a series of WebService Strings, can we access web services via a series of CSW endpoints and quantify those results?  And based on those results, is it apparent that some web services are not being discovered as they are utilizing variations on WebService Strings?

Methodology
*  Strings searched for in endpoints: services =      {'SOS'              : 'urn:x-esri:specification:ServiceType:sos:url',
                 'WMS'              : 'urn:x-esri:specification:ServiceType:wms:url',
                 'WCS'              : 'urn:x-esri:specification:ServiceType:wcs:url',
                 'DAP'              : 'urn:x-esri:specification:ServiceType:odp:url' }
 
<a name="theme2"/>
# Theme 2: Extreme Events 
The Extreme Events theme, as its name suggests, focuses on the analysis of data related to events that produce extreme adverse effects across a geographic area.  Possible topics within this theme may include, but not be limited to, the following:

<a name="scenario2A"/>
## Scenario 2A: Coastal Inundation
This scenario is nearing completion as of 11 July 2014.

The Python notebooks for this scenario can be found [here.](http://nbviewer.ipython.org/github/ioos/system-test/tree/master/Theme_2_Extreme_Events/Scenario_2A_Coastal_Inundation/)


As a severe storm is approaching the U.S. East Coast which will result in inundation, flooding, and wind damage over an extensive area. Coastal emergency managers must prepare for and respond to flooding as well as plan and implement evacuations.  Emergency managers, forecasters, and researchers currently rely on a number of data sources to do their work, including observations and forecast models:
* Forecasters are interested to know how federal and non-federal models compare to observed waves, river flows, and water levels, throughout the storm.
* Coastal emergency managers use inundation and flood data to identify where first responders should dedicate resources. 
* After the storm, researchers want to compare observed data to modeled data to identify model shortcomings and areas of improvement, as well as to quality control observing systems.

The ability to quickly and easily integrate these complementary datasets and predictions into visualizations and analyses will help emergency managers and responders improve their ability to forecast, prepare for and respond to coastal storms.


### Questions to Guide Corresponding IPython Notebooks

* Can we discover, access and compare modeled water levels, waves, winds, and currents by accessing a CSW/CKAN interface or multiple CSW/CKAN interfaces (See, [Service Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs) for all available water level models, and then constrain the output for an example bounding box and time period?
* Can we discover, access, and compare observed water levels, waves, winds, and currents from different agencies (e.g. USGS and CO-OPS) to modeled water levels, waves, winds, and currents within a particular bounding box and time period? 
* Is the associated metadata sufficient to provide necessary information about the datasets and to compare the different models and observations on the same reference frame / vertical datum?
* Can we discover, access, and overlay model data from both non-federal catalogs and federal catalogs?
* Can we discover, access, and overlay data from federal and non-federal river and coastal flood models including coastal elevation data and bathymetric data in a single IPython notebook?
* Can we discover, access, and overlay water quality data or inputs to statistical or dynamical water quality models (e.g. precipitation) to determine impacts of inundation to human health?
* Can we identify models or observations that are routinely used by the community but are not discoverable using these interfaces?
* Can we estimate the return period of a water level by comparing modeled and/or observed water levels with NOAA exceedance probability plots? 
* Can we use observed or modeled wind and water level data to help differentiate between flood and wind damage?
* Can we detect seiche events from Great Lakes water level data?  Can we characterize the meteorological forcing that caused a seiche?
* Can we plot the estimated extent of inundation (and associated depths) using USGS storm tide sensors and rapid deployment gages?


### Required Data to Answer Questions (source identified in parentheses):

- High resolution coastline
- Nearshore bathymetry
- Precipitation [NWS Radar] (http://www.nws.noaa.gov/gis/otherpage.html)
- Water quality ([USGS/EPA Water Quality Web Services] (http://qwwebservices.usgs.gov/) and fecal bacteria indicators
- Presence of jellyfish/HABs
- [USGS Flood Information](https://water.usgs.gov/floods/events/2012/sandy/sandymapper.html) Data
    * [SandyMapper](http://54.243.149.253/home/webmap/viewer.html?webmap=c07fae08c20c4117bdb8e92e3239837e)
- Near real-time water levels (NOAA)
- Long-term coastal tidal gauges (USGS, NOAA, USACE) [NOAA Tides Online](http://tidesonline.nos.noaa.gov/plotcomp.shtml?station_info=8410140+-+Eastport,%20ME&type=Tide+Data)
- Long-term stream gauges (USGS)
- Rapid deployment tide gauges (USGS - e.g. https://water.usgs.gov/floods/events/2011/irene/SurgeAndRDG.html)
- Rapid deployment stream gauges (USGS)
- Wave heights sensors (NOAA, IOOS Regions)
- Barometric pressure data (NOAA NOS, NOAA NWS)
- Coastal and ocean wind data (NOAA, IOOS Regions)
- High-water marks (USGS, NOAA, FEMA)
- Coastal wave and circulation models (USACE, NOAA, IOOS Regions)
- River stage forecast models (NOAA)
- SLOSH Model (NOAA NHC)
- ASGS (NOAA NOS)
- HFRADAR
- ESTOFS Surge Model, Hurricane Wave Model, etc. (NOAA NWS -[NOMADS Access](http://nomads.ncep.noaa.gov/))
- OFS Models (NOS - [OFS Model Page] (http://tidesandcurrents.noaa.gov/models.html))
- Stevens Storm Warning System - [CMS Storm Warning System](http://hudson.dl.stevens-tech.edu/SSWS/)
- Rutgers ROMS ESPreSSO Model - [Model Link] (http://www.myroms.org/espresso/)
- NERACOOS Regional Resources Identified:
    *  NECOFS - [THREDDS Link] (http://www.neracoos.org/datatools/data_access/THREDDS)
    *  [Delaware Coastal Flood Monitoring System](http://www.coastal-flood.udel.edu/)
    *  [NERACOOS Coastal Flooding and Erosion Tool](http://www.neracoos.org/dataproducts/forecast/coastal_flooding_forecast/portland)
    *  [NERACOOS Water Level Display](http://p5.neracoos.org/products/modeldata/popup.html?page=popup&platform=hampton&model_type=NEC)
    *  [NERACOOS Water Level Obs/Model Viewer](http://www.neracoos.org/datatools/forecast/modelobs)

### Vertical temperature gradients in a storm forecast region?
Collect all in situ observations in a given geographical region and determine which are sufficient to calculate vertical gradients.  For those platforms with vertical profiles, search for one or more models covering the same area in time and space and compare models to obs.

<a name="scenario2B"/>
## Scenario 2B:  U.S. Integrated Coastal Flooding Information System
This scenario has not been touched as of July 11, 2014.  Unless there is a compelling case to be made for this scenario, it should not be pursued.
#####Northeast (or East Coast) Integrated Coastal Flooding Information System Product Description
The northeast coastal zone (or eastern seaboard) is subject to significant coastal storms such as hurricanes and nor’easters, which can result in significant damage to property and loss of life. Much of the impact from these storms is a result of coastal flooding and erosion. 

NWS forecasters are responsible for forecasting coastal hazards and issuing coastal warnings. Coastal emergency managers must prepare for and respond to flooding as well as plan and implement evacuations. Forecasters and emergency managers often rely on various and disparate data sources to perform there work. Some of the critical data sources used include observations from coastal water level monitoring stations as well as forecasted water level from a variety of models. Local observations of impacts and coastal land elevation data are also important data sources. Integrating these complementary data sets and predictions into a set of tools and displays that effectively delivers information to forecasters and emergency managers and responders could significantly improve their ability to forecast, prepare for and respond to coastal storms.

#####User Community Addressed
The primary user communities for this product are NWS marine forecasters, coastal emergency managers and responders and coastal resource managers. Additional stakeholders include coastal municipal officials and coastal property owners.

#####Questions to Guide Corresponding IPython Notebooks
This product will integrate critical coastal water level information from water level monitoring stations and various forecasts into a set of interactive visual tools. The displays will include both spatial and temporal display of observed and predicted water level and potential flooding.  The tools will allow the user to view one or more forecasts of water level and view what the predicted surge could be. Specific functional requirements include:
* Map displays of locations and/or regions that includes information about current water level and potential for flooding
* Presentation of observed, predicted, surge water height on an interactive graph
* Ability to set start and end dates of graphs
* Water level displays allow user to select among various datums (e.g. NAVD88, MLLW) and units (e.g. cm, inches)
* Water level display integrates local information about flooding if available
* When available allow user to view multiple forecasts of water level from different models
* Include a calculation of “consensus” prediction from various models
* Ability to look at data from past events
* Display street level flooding predictions in a map view where elevation and high resolution predictions are available

#####Impact
This integrated information product potentially has high impact because it will integrate critical observations and predictions into a tool that will allow NWS marine forecasters to view multiple predictions ultimately giving them more confidence and improved ability to predict coastal hazards. It will also give emergency managers and responders coastal water level information they need to more effectively prepare and respond to a coastal storm.

#####Feasibility
This product is highly feasible because many of the required elements currently exist but need to be integrated. There are real-time water level monitoring stations and various water level prediction models operating in the region. There are also data standards/services in place or available that would allow standardized access to observations and forecasts. Additionally, much of the functionality desired for this integrated product already exists in various products (see listing below) and could be enhanced and brought together into an integrated tool. 

####Existing water level and coastal flooding products that have components of the functionality desired in an integrated product:
*  [NOAA Tides Online](http://tidesonline.nos.noaa.gov/plotcomp.shtml?station_info=8410140+-+Eastport,%20ME&type=Tide+Data)
*  [CMS Storm warning system](http://hudson.dl.stevens-tech.edu/SSWS/)
*  [Delaware Coastal Flood Monitoring System](http://www.coastal-flood.udel.edu/)
*  [NERACOOS coastal flooding and erosion tool](http://www.neracoos.org/dataproducts/forecast/coastal_flooding_forecast/portland)
*  [NERACOOS Water Level Display](http://p5.neracoos.org/products/modeldata/popup.html?page=popup&platform=hampton&model_type=NEC)
*  [NERACOOS water level obs/model viewer](http://www.neracoos.org/datatools/forecast/modelobs)

<a name="scenario2C"/>
## Scenario 2C: Oil Spill Response Modeling
Not under development as of July 11, 2014. Is this scenario feasible to pursue in the next 45 days?
An oil tanker loaded has collided with another vessel 5 nautical miles SE of the entrance to Delaware Bay _(NOTE: can we use another coast, maybe SF Bay?)_.  A large quantity of oil has been released into the marine environment, threatening the shoreline of a particular coastline. 

#### Questions to Guide Corresponding IPython Notebooks
* Can we discover, access and map high resolution coastline data and observed real-time sea surface current vectors in a designated bounding box for a designated time?
* Can we discover, access and map model projections of sea surface current vectors in a designated bounding box over a future period of time? 
* Can we discover, access and map satellite remote sensing data of sea surface currents against observations and modeled projections of sea surface currents in a single IPython notebook?
* Can we discover, access and map coastline, bathymetry, tides, waves, currents, winds, and overlay these values with data reflecting coastal ecological vulnerabilities in a designated bounding box for a designated time? 
* Can we discover, access and overlay data relating to the [core IOOS biological variables](http://www.iooc.us/activities/biological-integration-observation-task-team/)? 
* Can we discover, access and map an oil spill trajectory using GNOME for a particular location?  
    *  Answering this question will also mean answering the question of whether we can discover, access and use wind speed and river flow rates in a single script, and consequently call the GNOME model to run the scenario after entering a specified spill size, location, pollutant type, model duration, and uncertainty (See, [GNOME Example Problem Document](http://response.restoration.noaa.gov/sites/default/files/Gnome_NSlope_Ex.pdf)). 
    * Consider reaching out to OR&R to discuss this test case.

####Required Data to Answer Questions
* Wind speed/direction (NOAA, IOOS Regions)
* Wave direction and height (NOAA, IOOS Regions)
* Surface currents and direction (e.g IOOS high-frequency coastal radar, IOOS/NOAA current meters)
* Synthetic aperture radar (SAR) data
* Satellite remote sensing data (e.g. Advanced Scatterometer (ASCAT METOP-A))
* Near real-time water levels (NOAA)
* Long-term coastal tidal gauges (USGS, NOAA, USACE) [NOAA Tides Online](http://tidesonline.nos.noaa.gov/plotcomp.shtml?station_info=8410140+-+Eastport,%20ME&type=Tide+Data)
* Long-term stream gauges (USGS)
* Rapid deployment tide gauges (USGS)
* Rapid deployment stream gauges (USGS)
* Water density
* High resolution coastline data
* Shoreline types 
* Bathymetry 
* Threatened and endangered species data (NOAA NOS, BOEM)
* Societal boundaries (vessel traffic, shipping lanes, state/territorial waters boundaries) 
* [IOOS Core Biological Variables](http://www.iooc.us/activities/biological-integration-observation-task-team/)
* RESOURCES Consulted:
    *  [Maritime Environmental Emergency Oil Spill Trajectory Model](http://www.amsa.gov.au/environment/maritime-environmental-emergencies/national-plan/General-Information/OSTM/faq/answers.asp)
    *  [NASA Imagery of Oil Spills](http://www.nasa.gov/topics/earth/features/oilspill/index.html)
    *  [NOAA Ocean Service Oil Spill Trajectory Model](http://oceanservice.noaa.gov/education/stories/oilymess/supp_trajmodel.html)
    *  [General NOAA Operational Modeling Environment](http://response.restoration.noaa.gov/gnome)
    *  [Gulf of Mexico Research Initiative Data Discovery](https://data.gulfresearchinitiative.org/)

<a name="scenario2D"/>
## Scenario 2D: Search & Rescue - Commercial Aircraft Crash
Stop searching.  This scenario is beyond rescue.
A large commercial aircraft en route LAX from Honolulu with several hundred passengers onboard has crashed into the Pacific Ocean midway between the Hawaiian Islands and the California coast.  A massive search and rescue effort is underway.  This effort can be improved by integrated knowledge of the physical/chemical/biological conditions of the atmosphere and ocean.

###Questions to Guide Corresponding IPython Notebooks
* Can we discover, access, and map current weather conditions in a particular bounding box and overlay that with example coordinates of a crash site?
* Can we discover, access, and map a three day forecast of weather conditions in a particular bounding box and overlay that with example coordinates of a crash site?
* What models are available via CSWs that we can access through an IPython notebook, what are their URLs and can we call those models for the set bounding box, for a set of three days following the given date of a crash to compare modeled velocity vectors?
* Can we discover, access and map sea surface current maps from high frequency radar in near real time, and overlay this data with a particular crash site location using designated IOOS catalogs?  Can we do a similar analysis using regional IOOS catalogs?  Are there certain regions that stand out when we apply the script for IOOS catalogs to regional catalogs?

###Required Data to Answer Questions
* GPS location of crash site
* real-time weather 
* high frequency radar  
* wind speed/direction 
* surface currents
* wave heights
* sea surface temperature
* forecast wind speed/direction
* forecast surface currents
* forecast weather
* atmospheric visibility
* temperature (air and sea)
* cloud cover
* RESOURCES Consulted:
    *  [Data to Improve Coast Guard Search and Rescue](http://oceanservice.noaa.gov/news/weeklynews/may09/coastguard.html)
    *  [Search and Rescue Optimal Planning System](http://www.uscg.mil/acquisition/international/sarops.asp)
        *  [Description of SAROPS](http://www.sarapp.com/docs/SAROPS%20Description.pdf)

<a name="theme3"/>
# Theme 3: Species Protection & Marine Habitat Conservation
The mission of the NOAA National Marine Fisheries Service is to safeguard the viability of key marine species within the US economic zone.  That mission includes conserving sensitive marine habitat and restoring marine habitat that has been degraded by factors such as destructive fishing techniques and water pollution.  It also includes monitoring and protecting threatened marine species such as sea turtles and whales. The National Marine Fisheries service includes IOOS data in their assessments of habitat and threatened marine species.  Part of the value of integrating species and habitat data into the IOOS system is enabling the resolution of conflicts between human uses of our oceans and the protection of fragile marine habitats and the natural resources that they support.  Activities such as mineral extraction and energy siting require the use of a suite of marine habitat and species data in order to ensure that operations comply with marine conservation laws designed to require managers and policy makers to consider the ecological impacts of human activities.  

<a name="scenario3A"/>
###Scenario 3A: Identifying Factors Affecting Species Viability
As of July 11, 2014, the Bering Seabird version of this scenario has been taken about as far as it can reasonably go. Python notebooks should be submitted for pull requests ASAP.  Much of the code can and should be re-used to assess the viability of species in other areas where human activities might cause harm.  Such scenarios might include tuna viability in the Gulf of Mexico after the Deepwater Horizon spill, or Oyster viability in the Chesapeake Bay.Corresponding Python notebook can be found [here.](http://nbviewer.ipython.org/github/ioos/system-test/tree/master/Theme_3_Species_Protection_and_Marine_Habitat_Conservation/Scenario_3A_Assessing_Seabird_Vulnerability_in_the_Bering_Sea/)

The climate is changing in the Bering Sea and Aleutian Islands region. Residents, stakeholders, scientists, and natural resource managers are all concerned about the impacts of future climate change on important species, systems and habitats. But projections of future climate are uncertain, and different approaches have different strengths and limitations. With variation in projections, and with different impacts depending on species and systems of concern, how can stakeholders and managers realistically anticipate and plan for the impacts of climate change?

Over the past months, an interdisciplinary team of scientists has begun an effort to assess the vulnerability of  key resources and ecosystem services including marine mammals, fish and commercial fisheries, terrestrial vegetation, human community sustainability and seabirds. Vulnerability assessment is a well-developed, systematic way to “synthesize and integrate scientific information, quantitative analyses, and expert-derived information in order to determine the degree to which specific resources, ecosystems, or other features of interest are susceptible to the effects of climate change” (USFS 2011). The Aleutian and Bering Climate Vulnerability Assessment (ABCVA) proposed to integrate model projections from two recent climate downscaling approaches; one from the Bering Sea Project, and one from the Spatial Tools for Arctic Mapping and Planning (STAMP). Both of these model outputs were ingested into the AOOS data system and results were shared with a team of 30 leading researchers and managers at the recent Alaska Marine Science Symposium in January. Since then, volunteer teams of expert working groups have begun to develop preliminary vulnerability assessment.  Teams have identified specific information gaps and questions of greatest relevance to resource managers and other stakeholders in the region relative to projected changes in climate. 

One team, focused on seabirds, has identified the need for an analytical process that would allow the the exploration of multiple climate projection data sets.  This analytical process, described below, provides an ideal opportunity to evaluate the DMAC system integration capabilities within an existing project with Federal and non-Federal partners and Regional Associations. This project is a collaboration between the Aleutian and Bering Sea Islands Landscape Conservation Cooperative (ABSI LCC), the Alaska Climate Science Center and the Alaska Ocean Observing System (AOOS). It represents approximately a $150,000 investment, contributed in-kind staff time from the three organizations leading the effort, as well as substantial investments of in-kind investments from the 30 members that make up our 5 focal teams.
The seabird team, which includes collaborators from Audubon Alaska and the U.S. Fish and Wildlife Service, has identified the need for a change detection analysis using 13 projected climate, and climate-derived, raster data layers within the boundaries of Audubon’s recently established  Important Bird Areas (IBAs). Important Bird Areas are zones of high biological productivity and conservation priority for marine bird species extend throughout the Pacific Flyway up the coast of North America, from Mexico to the Gulf of Alaska, through the Bering Sea and into the Arctic Ocean (Smith et al. 2014). Almost 80% of the breeding seabirds within the U.S. are dependent on the Bering Sea and Aleutian Islands making IBAs within our study region especially important.  This process will enable access to complex model outputs, and will create new pathways to discover and explore a broad suite of projected model variables that impact seabirds. Pairing this change detection analysis with expert knowledge on seabird ecology will strengthen the ability of managers to proactively plan for seabird monitoring and conservation. 

Opportunities to replicate and adapt the workflow processes established by the IOOS System Integration Test could include any other regions where user-defined polygons and IOOS held model projects can be used to define statistical reports for IOOS resources using open-source computing resources. Other examples include using a very similar process to explore the projection space with IBAs in California using the same types of models, or marine mammal distribution areas and how they relate to projections of food sources (e.g., foraging areas associated with rookeries for northern fur seals and Steller sea lions have similarly been identified by NOAA managers). The proposed IPython Notebooks could also be used to explore projected changes in the marine ecosystem and how they relate to Essential Fish Habitat maps.

####Questions to Guide Corresponding IPython Notebooks

Can all the PMEL models and their corresponding variables be adequately discovered and accessed using IOOS tools?

Can we discover, access, and overlay Important Bird Area polygons (and therefore other similar layers for additional important resource areas) on PMEL climate projections for the Bering Sea?

Is metadata for projected climate data layers and Important Bird Area polygons sufficient to determine a subset of polygons desired by a query?

Can a simple set statistics (e.g., mean and standard deviation) be derived from multiple variables in each of the six models to derive the forecast variability of climate conditions through time, through the end of the model runs (2003-2040)?

Can we create a standardized matrix or other display method for output variables that allow resource experts to easily assess projected changes in climate variables, within given ranges of time, and compare projected changes across multiple coupled oceanographic and climate models?

Can we develop a set of process-specific guidelines and a standardized set of outputs for a tool that would allow researchers to address a diversity of resource management questions relative to projected changes in climate for specific zones of interest?

####Data Required to Answer Questions

*  Important Bird Areas (IBAs) defined by the Arctic Marine Synthesis study (http://portal.aoos.org/?v=rand&portal_id=25#metadata/cd96fa58-aeb5-11e2-8a9a-00219bfe5678)
*  PMEL-run Model Forecasts for Bering Sea (hosted by AOOS) that are oceanographic-climate coupled models:
    *  ECHO-G
    *  CCCma
    *  MIROC

####Variables contained in each PMEL Model:
*  Sea Water Temperature
*  Small Phytoplankton Concentration
*  Euphausiids Concentration
*  Benthic Infauna
*  Current Velocity
*  Benthic Detritus Concentration
*  Small Coastal Copepod Concentration
*  Large Microzooplankton Concentration
*  Neocalanus Concentration
*  Large Phytoplankton Concentration
*  Offshore Neocalanus Concentration
*  Ice Phytoplankton Concentration
*  Sea Ice Area Fraction

If time permits, secondary PMEL-produced models could also be tested (but results kept separate from the above)
*  FORECAST
*  NCEP CFS-R
*  CLIVAR

Other oceanographic-only models held by AOOS that could be tested for changes in projected climate variability (but not projected biological variability) include:
SNAP AR5 Climate Models from AR5 GFDL-CM3, RCP 6.0 (Near Surface Winds, Air Temperature)
SNAP AR5 Climate Models from AR5 MRI-CGCM3, RCP 6.0 (Near Surface Winds, Air Temperature)
SNAP AR5 Climate Models from AR5 IPSL-CM5A-LR, RCP 6.0 (Near Surface Winds, Air Temperature)
SNAP AR5 Climate Models from AR5 GFDL-CM3, RCP 8.5 (Near Surface Winds, Air Temperature)
SNAP AR5 Climate Models from AR5 MRI-CGCM3, RCP 8.5 (Near Surface Winds, Air Temperature)
SNAP AR5 Climate Models from AR5 IPSL-CM5A-LR, RCP 8.5 (Near Surface Winds, Air Temperature)
SNAP Projections of Sea Ice Area Fraction from CESM-CAM5, CMCC-CM, ACCESS-1, MIROC-5, and HAD-GEM2-AO

<a name="scenario3B"/>

##Scenario 3B: Continental Shelf Use Case 
No development on this scenario as of July 11, 2014.  While interesting, this scenario is not feasible for development within the next 45 days.

The Cold Pool is a distinctive, along-shelf band of remnant winter bottom water over the mid and outer continental shelf particular to the area between the Northeast Peak of Georges Bank and Cape Hatteras. The Cold Pool is defined by its low temperature, and develops after the water column stratifies due to increased solar insolation, local fresh water runoff, and reduced wind mixing in April and May each year. Because the Cold Pool is bottom-trapped, it is virtually undetectable by ocean surface remote sensing measurements. Thus, existing pictures of Cold Pool distribution are aliased, incomplete, and one of the most poorly understood major Mid Atlantic Bight (MAB) features. The dynamics of this water mass has a disproportionately large role in structuring the biogeochemistry and ecology of the Mid-Atlantic continental shelf. For example the Cold Pool provides a thermal refuge for important fish species. This water mass also influences tropical storm and hurricane intensity.  

####Questions to Guide Corresponding IPython Notebooks

Currently there is no annual picture of trends or change in the Cold Pool along with its the associated biogeochemistry and biology of this region.

Can we discover, access, and combine multiple surface and in situ data sets housed in a variety of data repositories, available regional and basin scale models, remote sensing, and seasonal weather data/models? 

Can the available assets be easily extracted to create a dynamic visualization of the Cold Pool and the associated correlations to any available biology and chemistry. This test case would then phase in the Ocean and Observatory Initiative's [Pioneer Array](http://www.whoi.edu/ooi_cgsn/pioneer-array) as it comes online. 

Assets that the Broker(s) would potentially access:
*  NOAA IOOS regional RAs (Neracoos, Maracoos, Secora): Access the data [moorings, weather stations, gliders, HF CODAR, as well as any available regional model simulations (ROMs)]
*  Navy HyCOMM and/or NOAA RTOFS
*  Historical physical/chemical/biological data from the region from BCO-DMO
*  NASA ocean color and sea surface temperature
*  OOI Pioneer Array
*  NSF BCODMO data repositories

<a name="scenario3C"/>
##Scenario 3C: Deep Blue Water Use Case 
No development on this scenario as of July 11, 2014.  While interesting, this scenario is not feasible for development within the next 45 days.

A large community of NSF-funded, field biological and chemical oceanographers utilize the BCODMO data repositories (http://bco-dmo.org/), and a science use-case built to utilize BCO-DMO provides a good entry point for accessing the ocean science "dark data" collected by individual researchers and small teams. BCO-DMO hosts a wide range of data products, primarily discrete data collected from water samples and continuous data from underway instruments and profiling instruments.
####Questions to Guide Corresponding IPython Notebooks
Can we compare contemporaneous data from other field programs with ship based field programs in the regional context, VOS lines, autonomous platform networks, satellite remote sensting, and ocean and atmospheric model handcarts.

Can we overlay ship cruise tracks with aggregate contemporaneous regional data from other repositories.

Can we extract and aggregate data for regional bounding boxes (on the order of 10 by 10 degrees) centered on the four global OOI moorings(Irminger Sea, Ocean Station Papa, Southern Ocean, Argentine Basin).

Assets that the Broker(s) would potentially access:
*  Historical data from the region from BCO-DMO
*  NASA ocean color and sea surface temperature
*  AVISO altimeter derived surface currents
*  Argo float vertical profiles (temperature, salinity, other properties)
*  VOS data for surface carbon dioxide (e.g. from SOCAT http://www.socat.info/)
*  Navy HYCOM
*  NCEP reanalysis

<a name="scenario3D"/>
## Scenario 3D:  Assessing Chesapeake Bay Biology
No development on this scenario as of July 11, 2014.  While interesting, this scenario is not feasible for development within the next 45 days.
The NMFS Chesapeake Bay Office is updating its assessment of Chesapeake Bay biology, using updated information from recent assessment of Bay habitat.  In particular, The Chesapeake Bay Office is preparing a forecast of dead zones in the Bay for the upcoming season, and how the dead zones might affect populations of blue crab and rockfish. 

### Questions to Guide Corresponding IPython Notebooks
* What are the forecast flows for major Bay tributaries?
* What are the levels of particulate matter in the Bay and major tributaries?
* What are the forecast nitrogen levels of the Bay and its major tributaries?
* What are the forecast levels of algae in the Bay?
* What is the forecast distribution of algae in the Bay?
* What is the density and distribution of  phytoplankton in the Bay?
* What is the density and distribution of zooplankton in the Bay?
* What are the latest estimates of blue crab and rockfish populations?
* What are the latest estimates of major species on which blue crab abd rockfish prey?

### Data Required to Answer Questions
* water quality measurement history of the Bay and major tributaries
* dissolved nitrogen levels in the Bay and major tributaries
* bathymetry of the Bay 
* basic stock survey data for blue crab
* basic stock survey data for rockfish
* historical distribution of dead zones in the Bay
* forecast flows of major Bay tributaries
* Bay salinity data
* Bay water temperature data
* dissolved oxygen data in the Bay and major tributaries

<a name="scenario3E"/>
## Scenario 3E:  Assessing the Quality of Baleen Whale Summer Feeding Grounds Off the New England Coast
No development planned for this scenario.  Leave it for the next Captain Ahab.
Major spring and summer feeding grounds for baleen whales are located off the New England Coast.  The NMFS Office of Protected Resources wishes to forecast the biomass off the New England Coast that is available to feed baleen whales during the upcoming spring and summer. 

### Questions to Guide Corresponding IPython Notebooks
* Where are the main baleen whale feeding grounds located?
* What is the bathymetry of the feed grounds?
* What is  the history of water tempature in the feeding grounds?
* What are the historical levels of phytoplankton in the feeding grounds?
* What are the historical levels of zooplankton in the feeding grounds?
* What is the historical density and distribution of major baleen whale species off the New England Coast (Right Whales, Finback Whales, Humpback Whales)

### Data Required to Answer Questions
* GPS data on whale feeding grounds
* bathymetry data for feeding grounds
* water temperature measurements
* phytoplankton and zooplankton survey data
* whale population survey data 

<a name="scenario3F"/>
## Scenario 3F:  Planning for Wind Turbine Sites using Ecosystem Base Approach
A state is is the process of delimiting an area off its coast that is suitable for the placement of a major wind turbine farm.  The state must adhere to a number of laws and implementing policies before it can formally delineate an area for wind turbine development and solicit bids.

### Questions to Guide Corresponding IPython Notebooks
* Pre-IPython Notebook Policy Question and Policy-to-Data Mapping Exercise: What data is needed for particular energy planning policies (Outer Continental Shelf Lands Act, National Environmental Policy Act, etc.)?
* Can we discover, access, and overlay on a time series time series data for wind speed and direction for set of proposed wind turbine locations (lat, long) over the past 30 years?
* Can we discover, access, and overlay a map of proposed wind turbine locations with data sets showing ship traffic and/or other human uses (e.g. recreation, commercial fisheries, VMS data)?
* Can we discover, access, and overlay a map of proposed wind turbine locations with core IOOS variable data over a certain bounding box and/or ecologically sensitive areas and/or Marine Protected Areas designated by law?

### Required Data to Answer Questions
* wind 
* bathymetry
* land polygon for distance calculations
* global wind energy parameters
* turbine type
* minimum depth for offshore wind farm installation
* maximum depth for offshore wind farm installation
* minimum distance for offshore wind farm installation
* maximum distance for offshore wind farm installation
* habitat
* wildlife distribution
* migratory pathways
* sediment transport
* nutrients

<a name="scenario3G"/>
## Scenario 3G:  Mineral Extraction
No development on this scenario as of July 11, 2014. Is development of this scenario feasible within the next 45 days?
The Department of Interior Bureau of Ocean Energy Management is considering opening several tracts in the Gulf of Mexico for petroleum exploration. As part of their due diligence under regulations implementing the Outer Continental Shelf Lands Act, the Bureau must prepare an environmental impact statement before opening the tract to bids. The environmental impact statement must consider the potential impact of exploration and drilling on area fisheries.

### Questions to Guide Corresponding IPython Notebooks
*  Can we discover, access and map phytoplankton species and abundance trend in an area of interest over the past 30 years? 
*  Can we discover, access and map zooplankton species and abundance trend in an area of interest over the past 30 years? 
*  Can we discover, access and map fish species and abundance trend in an area of interest over the past 30 years? 

### Data Required to Answer Questions
* high resolution coastline
* bottom type
* bathymetry
* phytoplankton species and abundance
* zooplankton species and abundance
* fish species and abundance
* water quality metrics

<a name="scenario3H"/>
## Scenario 3H:  Exploring environmental changes affecting Polar Bears
As of July 11, Derrick to provide registry information to Kyle, who will finish the associated Notebooks.  Kyle estimates 8 hours of development time.

Python notebooks for this scenario can be found [here.](http://nbviewer.ipython.org/github/ioos/system-test/tree/master/Theme_3_Species_Protection_and_Marine_Habitat_Conservation/Scenario_3H_Exploring_Environmental_Changes_Affecting_Polar_Bears/)
Polar bears were the first vertebrate species to be listed by the U.S. Endangered Species Act as threatened by extinction primarily because of climate change. Polar bears use persistent sea ice as a platform from which to hunt seals. However, as Arctic sea ice recedes, they have to swim further from shore to reach it and, ultimately, have a shorter hunting season. Additionally, the new sea ice edge may lie over unproductive waters.

### Questions to Guide Corresponding IPython Notebooks
*  Can we discover, access and map polar bear denning locations?
*  Can we discover, access and map the sea ice edge using NSIDC passive microwave satellite data?
*  What is the distance between polar bear denning locations and the closest sea ice edge through time?
*  What is the minimum distance between the shoreline containing known polar bear distributions and the closest sea ice edge through time?
* Are certain sections of the coastline more susceptible to long distances from sea ice?

### Data Required to Answer Questions
* polar bear denning locations: [at USGS](http://pubs.usgs.gov/ds/568/) | [at AOOS](http://portal.aoos.org/#metadata/13a03d02-4296-11e2-88f7-00219bfe5678)
* NSIDC Sea Ice data: [at NSIDC](http://nsidc.org/data/nsidc-0051)| [at AOOS](http://thredds.axiomalaska.com/thredds/ncss/grid/NSIDC_SEA_ICE_CON.nc/dataset.html)
* high resolution coastline
* polar bear distribution: [at AOOS](http://portal.aoos.org/#metadata/cd96d028-aeb5-11e2-8653-00219bfe5678)


# RESOURCES AND REFERENCES FOR TESTING APPROACH

# Source for Test Cases

The the GEOSS Architecture Implementation Pilot, Phase 3, [Use Case Engineering Report](http://www.ogcnetwork.net/pub/ogcnetwork/GEOSS/AIP3/documents/AIP-3_Use_Cases_ER110210.pdf) provides a set of use cases that are relevant to DMAC and distributed data networks in general but are not science focused.   They may be useful as templates for building procedures for various DMAC test cases.  These so called transverse use cases may be useful in helping us standardize the data we will collect from each test case. [Note that the term "transverse use case' is not defined in systems testing literature and seems to be particular to the GEOSS Architecture Implementation Pilot project.]   

*  Nota Bene: The structure and style of the GEOSS use cases should not be lifted and used without revision in DMAC testing. Rather, the GEOSS use cases can suggest procedures that can be easily adapted to test DMAC functionality.  Of particular interest to DMAC are three GEOSS general use cases:

* DISCOVERY: Search for Resources
* ACCESS: Present Services
* USE: Exploit Data Visually and Analytically