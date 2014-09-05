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

# Structure of the test

* Conduct of the test

* Results and Findings

  * a. New or Revised Requirements

  * b. State of initial operating capability of IOOS
###Model Strings (1A)
* Able to query many different CSW servers on a variety of model strings
* Able to summarize service types by model, service type, and source URL.
### Winds (Scenario 2A)
* Observation datasets containing wind speed and direction were discovered, accessed, and plotted for multiple stations in the Gulf of Mexico.
* Catalog-driven search using OGC CSW allowed for dynamic updating as new datasets become available (or inactive).
* Data from both OPeNDAP-CF and SOS endpoints were discovered, accessed and used. The accessing of SOS endpoint leveraged IOOS driven tools (PYOOS).
* Forecast model datasets were discovered, accessed, and plotted for points near the observation stations.
* Standards-based tools allowed extraction of NOAA/NCEP GFS structured grid model output, courtesy of the British Met Office Iris package.
* Time series plots were created visualizing wind speed and gusts on a single plot for observation stations  and wind direction .
* An inline interactive map interface displays the locations of observation data and corresponding model grid points. A line was drawn on the map to show the distance between observation stations and the corresponding nearest model grid point.
* Modeled and observation data were compared via a time series plot.

  * c. Evaluation of  the level of regional adoption of DMAC

  * d. Identified priority data sets that support the selected scenarios

  * e. Identified system constraints, especially regarding performance.
### Easy Issues That Have Been Resolved

####Wind Data (2A)
* Some models have different longitude conventions ([0 360] and [-180 180]). This was accounted for by converting all longitude values to [-180 180].
* Of all the CSW endpoints tested NGDC and NODC were the only ones with very recent wind data available. The NGDC CSW end point was used.
* As of 07/31/2014, the NOAA/NCEP GFS model can't be accessed.

  * f. Reusable aspects of framework that can be used in future tests and continuing integration

* Recommendations