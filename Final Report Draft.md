# Background
The distributed, service oriented architecture of DMAC has been implemented independently by IOOS partners, using different software approaches and different levels of implementation.  IOOS partners differ in their online data discovery and access protocols they offer, the percent of their datasets available through their online services, and the percent of datasets registered with the IOOS catalog.  These differences can present difficulties to researchers and policy makers who are looking for oceanographic data to address important scientific endeavors and policy issues.

# Objective

The DMAC system integration test (DMAC-IT) evaluates the extent to which the services that IOOS has deployed  to Federal partners and Regional Associations can assist resarchers and policy makers in finding, accessing and using oceanographic data to address important research questions and policy issues.  IOOS services tested include the following:

* OPeNDAP Data Access Protocol (DAP) and/or Open Geospatial Consortium (OGC) Web Coverage Service (WCS) for access to gridded data
* OGC Sensor Observation Service (SOS) for access to in situ observations
* OGC Web Map Service (WMS) for access to geo-referenced image data
* OGC Catalog Service for the Web (CSW)

The DMAC-IT varies from the common notion of system integration test in two important ways:

1. The DMAC architecture is not one system, but rather, a system of systems, each one operated by an IOOS partner, and each one largely outside of IOOS control. Therefore, the IOOS DMAC team cannot control the configuration of IOOS member data registries and repositories.  One consequence is that an IOOS member can make changes to their system that invalidate previous successful DMAC tests.  Therefore, the results of a particular DMAC-IT test for a particular IOOS partner site are reliable only so long as the configuration of the partner's data resources remains unchanged.  IOOS parnters frequently alter the configuration of their data resources without informing the IOOS program office. Although the DMAC-IT project has an end date, the process of testing whether an IOOS partner's data resources can be identified, accessed and used will be an ongoing operation.

2. The protocols the DMAC-IT has used to identify, access and use data are in varying states of maturity.  Some of them have been widely adopted by IOOS partners, while others are in the early stage of adoption.  Because the IOOS partners do not yet have a fully standardized set of protocols, a service that might work for 6 partner sites might not work for another 4.  In this context, success is defined as knowing which service protocols work for which IOOS partner sites.

The objective of the DMAC-IT is to assess the current level of maturity of DMAC, as measured by the the extent to which Open Geospatial Consortium (OGC) standard query tools and techniques can successfully identify, access and use information from IOOS data providers.  

# Testing Framework
The approach for DMAC-IT has been to package discrete test scenarios and their scripts within larger contexts called _themes_. Each theme provides one or more _scenarios_ that generates specific questions that require discovery, access and use of appropriate metadata and data. The themes provide a realistic testing framework within which to frame and and address public policy questions with IOOS data.

Within each theme there is a top level _problem statement_, which contains the overall objective of the theme. For a theme with more than more objective, two or more scenarios will address particular objectives within the theme. Themes are accompanied by IPython Notebooks which address particular questions under each theme. Each IPython notebook includes comments that identify the theme for which the notebook is used, the question areas that the notebook addresses, the results from executing the python scripts, and the conclusions that can be drawn from the results. A particular IPython notebook may address questions of discovery, questions of access and questions of use.

IPython notebooks use the following common format:

Theme Title
Scenario Description and Title
Questions
DISCOVERY Process (code and narrative)
ACCESS Process (code and narrative)
USE Process (code, narrative, and graphics where appropriate)
Results and Conclusions (narrative)

The procedures employ IPython scripts that interrogate DMAC registries and repositories, and analyze the returned data against expected results. There is not necessarily a one-to one correspondence between a Question and a notebook product. Each question may correspond to a number of notebooks in order to increase readability and modularity of the IPython notebook tools.

# Test Themes
## Theme 1: Baseline Assessment
The baseline assessment theme includes test scenarios that, as the name of theme states, assess the basic functionality of DMAC.  While the test scenarios for this theme have no focus on a particular scientific endeavor, the functionality to be tested underlies all subsequent test themes. These scenarios incorporate multiple IOOS Regions and partners, cover a large geographic scope, employ multiple types of data, and cross scientific disciplines. Results from baseline scenarios include:

* Basic statistics on the number and type of data sets in each chosen registry or catalog
* Metadata standards and dialects employed within those registries
* Statistics on the number of types of service protocols/endpoints to access the data
* For a given area of interest, a listing of the total number of variables/data sets available in a given catalog, as well as a listing of the variables in the catalog

The following general questions have been used to guide the development of IPython notebooks within the Baseline Theme.

* What are the essential elements that determine whether a search has been successful?
* What are the interfaces that a particular catalog provides (html page with forms, csw, opensearch, ckan etc)?
* What are the contents of a given registry when summarized along several important query parameters?
* What variable names (IOOS core variables, CF standard names etc) appear within a given registry?
* Which well-defined service interfaces are present for a given registry?
* For a given registry, are clear, human-readable titles/abstracts/summaries/identifiers contained in the metadata?
* Within a given registry are there present keywords and references to standardized keyword vocabularies (preferably machine readable)?

### Scenario 1A: Model Strings

####Guiding Question 
Can we pull out model records from CSW endpoints based on a series of model strings? And, based on this exercise, is there a need for standardized model strings in order to ensure the discoverability of these records?

####Methodology
Strings searched for in endpoints: model_strings = ['roms','selfe','adcirc','ncom','hycom','fvcom']
Notebook provides a data frame with listed endpoints, records, titles of records, and title lengths.

###Scenario 1B: Core Variable Strings

####Guiding Question 
Using a list of Core IOOS Variables and the SPARQLWrapper vocabulary mapping tool, can we search and quantify records from CSW endpoints that relate to core variables?

####Methodology
Strings searched for in endpoints: var_key = ['fish','phytoplankton','zooplankton']
Notebook provides code that utilizes SPARQLWrapper tool
Notebook provides output in the form of a dataframe listing endpoints searched, records, record titles, and length of records.

####Unresolved Question
The use of SPARQLWrapper does not seem to enhance the search terms based on Core IOOS variables.

###Scenario 1C: WebService Strings

####Guiding Question 
Based on a series of WebService Strings, can we access web services via a series of CSW endpoints and quantify those results? And based on those results, is it apparent that some web services are not being discovered as they are utilizing variations on WebService Strings?

####Methodology
Strings searched for in endpoints: services = {'SOS' : 'urn:x-esri:specification:ServiceType:sos:url', 'WMS' : 'urn:x-esri:specification:ServiceType:wms:url', 'WCS' : 'urn:x-esri:specification:ServiceType:wcs:url', 'DAP' : 'urn:x-esri:specification:ServiceType:odp:url' }

###Scenario 1D: Dissolved Oxygen Data

####Guiding Question 
Based on a series of keywords, can we access dissolved oxygen data through CSWs or other means? Any issues with finding dissolved oxygen data?

####Methodology
data_dict["doxygen"] = {"names":['fractional_saturation_of_oxygen_in_sea_water', 'mass_concentration_of_oxygen_in_sea_water', 'mole_concentration_of_dissolved_molecular_oxygen_in_sea_water', 'moles_of_oxygen_per_unit_mass_in_sea_water', 'volume_fraction_of_oxygen_in_sea_water', 'oxygen'], "sos_name":["doxygen"]}

###Scenario 1E: Salinity Data

####Guiding Questions
Based on a series of keywords, can we access dissolved oxygen data through CSWs or other means? Any issues with finding dissolved oxygen data?

####Methodology 
data_dict["salinity"] = {"names":['salinity', 'sea_surface_salinity', 'sea_water_absolute_salinity', 'sea_water_practical_salinity', 'sea_water_salinity'], "sos_name":["salinity"]}

##Theme 2:  Extreme Weather/Water Events

### Scenario 2A:  Wind-Related Factors

####Guiding Question
Can we compare observed and modeled wind speeds at stations located within a bounding box? 

####Methodology
* Define temporal and spatial bounds of interest, as well as parameters of interest
* Search for available service endpoints in the NGDC CSW catalog meeting search criteria
* Extract OPeNDAP data endpoints from model datasets and SOS endpoints from observational datasets
* Obtain observation data sets from stations within the spatial boundaries
* Using DAP (model) endpoints find all available models data sets that fall in the area of interest, for the specified time range, and extract a model grid cell closest to all the given station locations
* Plot observation stations on a map (red marker for model grid points) and draw a line between each station and the model grid point used for comparison
* Plot modeled and observed time series wind speed on same axes for comparison

###Scenario 2B:  U.S. Integrated Coastal Flooding Information System

####Guiding Question
Can we estimate the return period of a water level by comparing modeled and/or observed water levels with NOAA Annual Exceedance Probability Curves?

####Methodology


* Conduct of the test

* Results and Findings

  * a. New or Revised Requirements

  * b. State of initial operating capability of IOOS



* Recommendations