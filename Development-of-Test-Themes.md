# Introduction
The entire project is organized into phases or focus areas called themes.  Themes will focus on a large problem area and will be used to identify common problems or needs commonly encountered by  data consumers who work within these theme areas.  These theme areas are similar to the GEOSS societal benefit areas.  

Within each theme there is a top level problem statement, which contains the overall objective of the theme.  Themes will be accompanied by IPython Notebooks which address particular questions under each theme.  Each IPython notebook will include comments that identify the theme for which the notebook is used, the question areas that the notebook addresses, the results from executing the python scripts, and the conclusions that can be drawn from the results.  A particular IPython notebook may address questions of discovery, questions of access and questions of use.

IPython notebooks will be standardized using the following format:

*  **Theme Title**
       *  _**Questions**_
         *  DISCOVERY Process (code and narrative)
         *  ACCESS Process (code and narrative)
         *  USE Process (code and narrative)
    *  _**Results and Conclusions**_ (narrative)
         
The procedures will employ IPython scripts that interrogate DMAC registries and repositories, and analyze the returned data against expected results.  There is not necessarily a one-to one correspondence between a Question and a notebook product.  Each question may correspond to a number of notebooks in order to increase readability and modularity of the IPython notebook tools.   

# Theme 1: Baseline Assessment
The baseline assessment theme includes test cases that, as the name of theme states, assess the basic functionality of the Data Management and Communications system. While the test cases for this theme have no slant towards a particular scientific endeavor, the functionality to be tested underlies all subsequent test themes.  To put it simply, the Baseline Assessment theme tests whether registries, catalogs, metadata sets and data sets that are known to meet IOOS certification can be discovered, accessed and used. Results include information such as basic statistics on the number of data sets in each chosen registry, the standards advertised, and the dialects of the metadata within the registries. Information obtained through the use of IPython scripts will be compared against corresponding information retained by a registry, catalog, or data repository owner to answer the question below.

### Questions to Guide Corresponding IPython Notebooks

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
The Extreme Events theme, as its name suggests, focuses on the analysis of data related to events that produce extreme adverse effects across a geographic area.  Possible topics within this theme may include, but not be limited to, the following:

## Theme 2A: Severe Coastal Storm
As a severe storm is approaching the U.S. East Coast which will result in inundation, flooding, and wind damage over an extensive area. Coastal emergency managers must prepare for and respond to flooding as well as plan and implement evacuations.  Emergency managers, forecasters, and researchers currently rely on a number of data sources to do their work, including observations and forecast models:
* Forecasters are interested to know how federal and non-federal models compare to observed waves, river flows, and water levels, throughout the storm.
* Coastal emergency managers use inundation and flood data to identify where first responders should dedicate resources. 
* After the storm, researchers want to compare observed data to modeled data to identify model shortcomings and areas of improvement, as well as to quality control observing systems.

The ability to quickly and easily integrate these complementary datasets and predictions into visualizations and analyses will help emergency managers and responders improve their ability to forecast, prepare for and respond to coastal storms.


### Questions to Guide Corresponding IPython Notebooks

* Can we discover, access and compare modeled water levels by accessing a CSW/CKAN interface or multiple CSW/CKAN interfaces (See, [Service Registries and Data Catalogues](https://github.com/ioos/system-test/wiki/Service-Registries-and-Data-Catalogs) for all available water level models, and then constrain the output for an example bounding box and time period?
* Can we discover, access, and compare observed water levels from different agencies (e.g. USGS and CO-OPS) to modeled water levels within a particular bounding box and time period? 
* Is the associated metadata sufficient to provide necessary information about the datasets and to compare the different models and observations on the same reference frame / vertical datum?
* Can we discover, access, and overlay model data from both non-federal catalogs and federal catalogs?
* Can we discover, access, and overlay data from federal and non-federal river and coastal flood models including coastal elevation data and baythmetric data in a single IPython notebook?
* Can we discover, access, and overlay water quality data or inputs to statistical or dynamical water quality models (e.g. precipitation) to determine impacts of inundation to human health?
* Can we identify models or observations that are routinely used by the community but are not discoverable using these interfaces? 


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
- Rapid deployment tide gauges (USGS)
- Rapid deployment stream gauges (USGS)
- Wave heights sensors (NOAA, IOOS Regions)
- Barometric pressure data (NOAA NOS, NOAA NWS)
- Coastal and ocean wind data (NOAA, IOOS Regions)
- High-water marks (USGS, NOAA, FEMA)
- Coastal wave and circulation models (USACE, NOAA, IOOS Regions)
- River stage forecast models (NOAA)
- SLOSH Model (NOAA NHC)
- ASGS (NOAA NOS)
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

## Theme 2B: Oil Tanker Spill
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

## Theme 2C: Search & Rescue - Commercial Aircraft Crash
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


# Theme 3:   Ecologically Sustainable Marine Energy Planning
The driver behind many state based marine conflict resolution programs has been the siting of energy projects. Because state and federal governments working to site new energy or additional ocean energy extraction in state/federal waters must consider a suite of existing uses, including species and areas of biological importance, siting energy implicitly requires governments and private entities to utilize and overlay ecological data sets with physical data sets.  Therefore, planning for marine energy presents an ideal way to test the IOOS system for both physical and biological data that is needed to plan for energy extraction in the ocean in an ecologically sustainable way.   

## Theme 3A:  Planning for Wind Turbine Sites using Ecosystem Base Approach
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

## Theme 3B:  Mineral Extraction
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

* RESOURCES Consulted:
    *  The [InVEST Model for Wind Energy Siting](http://ncp-dev.stanford.edu/~dataportal/invest-releases/documentation/current_release/wind_energy.html#required-inputs) is a good starting place for required data sets (See, "Required input" section in the link).
    *  [Wind Power Sitin, Incentives and Wildlife Guidelines in the United States](http://www.fws.gov/habitatconservation/windpower/afwa%20wind%20power%20final%20report.pdf) 
        *  This document provides a comprehensive break down of the laws and applications to energy siting and could be used as a starting point for mapping legislative and executive policy to required data sets for planning purpose.
  *  [Planning for Offshore Energy Development](http://www.analysisgroup.com/uploadedFiles/Publishing/Articles/Planning_for_Ocean_Energy_Development_Complete.pdf)
        *  This document covers both offshore oil/gas permitting and offshore wind permitting.
        *  See Table 1 for comprehensive list of legislation, subject matter, and responsible federal agencies that could serve as starting point for data to policy trace-ability mapping.

# RESOURCES AND REFERENCES FOR TESTING APPROACH

# Source for Test Cases

The the GEOSS Architecture Implementation Pilot, Phase 3, [Use Case Engineering Report](http://www.ogcnetwork.net/pub/ogcnetwork/GEOSS/AIP3/documents/AIP-3_Use_Cases_ER110210.pdf) provides a set of use cases that are relevant to DMAC and distributed data networks in general but are not science focused.   They may be useful as templates for building procedures for various DMAC test cases.  These so called transverse use cases may be useful in helping us standardize the data we will collect from each test case. [Note that the term "transverse use case' is not defined in systems testing literature and seems to be particular to the GEOSS Architecture Implementation Pilot project.]   

*  Nota Bene: The structure and style of the GEOSS use cases should not be lifted and used without revision in DMAC testing. Rather, the GEOSS use cases can suggest procedures that can be easily adapted to test DMAC functionality.  Of particular interest to DMAC are three GEOSS general use cases:

* Search for Resources
* Present Services
* Exploit Data Visually and Analytically