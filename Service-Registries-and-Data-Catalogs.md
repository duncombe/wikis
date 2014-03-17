1. List all of the catalog/registries we will include as part of the test.
2. List the service interfaces they provide.
3. Are the registries domain specific?
4. List a short description of each for inclusion in the final report.  What is the registry?  Who sponsors it?  Any domain specific issues?  

Some of these are taken from Rich's [blog](http://rsignell-usgs.github.io/blog/blog/2014/01/15/csw_ngdc_dap/)

* IOOS [Service Registry](https://geo-ide.noaa.gov/wiki/index.php?title=ESRI_Geoportal#IOOS_WAFs) at NGDC
  * csw: http://www.ngdc.noaa.gov/geoportal/csw
* NGDC Geoportal aka IOOS Registry
  * csw: http://www.ngdc.noaa.gov/geoportal/csw
* NODC Geoportal: granule level (aka UAF Geoportal)
   * csw: http://www.nodc.noaa.gov/geoportal/csw 
* NODC Geoportal: collection level 
   * csw: http://data.nodc.noaa.gov/geoportal/csw  
* data.noaa.gov
   * ckan: ???
   * csw: https://data.noaa.gov/csw?service=CSW&version=2.0.2&request=GetCapabilities
* data.gov
   * ckan: ???
   * csw: ???
* NRCAN CUSTOM
   * csw: http://geodiscover.cgdi.ca/wes/serviceManagerCSW/csw
* USGS Woods Hole GI_CAT
   * csw: http://geoport.whoi.edu/gi-cat/services/cswiso
* USGS CIDA Geonetwork
   * csw: http://cida.usgs.gov/gdp/geonetwork/srv/en/csw
* USGS Coastal and Marine Program
   * csw: http://cmgds.marine.usgs.gov/geonetwork/srv/en/csw 
* USGS Woods Hole Geoportal
   * csw: http://geoport.whoi.edu/geoportal/csw
* CKAN testing site for new Data.gov
   * csw: http://geo.gov.ckan.org/csw  
* EPA
   * csw: https://edg.epa.gov/metadata/csw
* CWIC
   * csw: http://cwic.csiss.gmu.edu/cwicv1/discovery
* West Coast Governors Alliance (Based on ESRI Geoportal back end)
   * api information: http://portal.westcoastoceans.org/connect/
*  NCEP Global Atmospheric Model/Best Time Series
   *  http://ferret.pmel.noaa.gov/geoide/CleanCatalogs/oos.soest.hawaii.edu/thredds/catalog/hioos/model/atm/ncep_global/catalog.html

####References For Creating and Documenting Baseline Test
*  Initial Baseline Approach: [Empirical Study of Sensor Observation Services Server Instances](http://arxiv.org/ftp/arxiv/papers/1109/1109.4503.pdf)

*  [Reference Document for Accessing and Examining CSWs](https://drive.google.com/file/d/0B8p4sUXIeKn1WFdYOXhqRFNUZXc/edit?usp=sharing)

*  [A Useful Slideshow about using Python to harvest CWS metadata](http://pycsw.org/publications/foss4g2013/#/) and [Associated Wiki Page](https://github.com/geopython/pycsw/wiki)

*  The NOAA/NGDC supported customizations for the ESRI Geoportal Server are available on the [NOAA EDM wiki](https://geo-ide.noaa.gov/wiki/index.php?title=ESRI_Geoportal#ISO_19115-2_support).  Check with Dave N to make certain they are up to date.