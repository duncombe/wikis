The Open Geospatial Consortium. Open Geospatial Consortium Reference Model. Informative/Educational, December 19, 2011. www.opengis.net/doc/orm/2.1.

CSW

OpenSearch

GEOSS AIP-6 Architecture Document http://www.earthobservations.org/documents/cfp/201302_geoss_cfp_aip6_architecture.pdf

GEOSS AIP-3 Use Cases Engineering Report GEOSS Architecture Implementation Pilot, Phase3, http://www.ogcnetwork.net/pub/ogcnetwork/GEOSS/AIP3/documents/AIP-3_Use_Cases_ER110210.pdf


Paper on DMAC technologies in support of modeling: https://docs.google.com/a/noaa.gov/file/d/0B8Z5uQGdxxJBcGk2UFlKU1IzOEpfS2NrMHV5M3k0dUlRM1dr/edit

Karl Benedicts presentation to the DMAC ST on 2013-11-19.

Here are links to the DATE project presentation materials for tomorrow morning's session:

    Presentation (self-contained web page. arrow-keys advance):  https://www.dropbox.com/s/ehlu0p3s7caxp8i/presentation.slides.html
    Notes (just an alternative format for the same content):  https://www.dropbox.com/s/0spmxekonaivneu/presentation.html 

Rich Signell's  presentation at the same meeting.

    The presentation I gave at the DMAC ST meeting is at: https://drive.google.com/file/d/0BzAHlPEEP_ujTHo2MHN0akdPLTA/edit?usp=sharing
    And here is one of the IPython Notebooks I showed that demonstrates  a simple example of Search, Access and Use using IOOS services:  https://www.wakari.io/sharing/bundle/rsignell/NGDC-CSW-DAP  It looks for temperature data in a specified geographic and temporal range from data that has been registered with the IOOS Catalog, accesses the data, and plots them up!  You can try it yourself by clicking the green "Run/Edit" button.   I recorded a 5 min youtube of how you do this here: https://www.youtube.com/watch?v=4NyMWK4as-U


Here's the FEMA report on post sandy:http://www.fema.gov/media-library/assets/documents/33772

#Rich Signell Notebooks By Category

###NetCDF4 files
--> ([NetCDF](http://www.unidata.ucar.edu/software/netcdf/docs/group__datasets.html) simply provides a way of opening datasets as files or remote access URLs and offers a library of functions to use on those datasets)
*  [National Data Buoy Center](https://www.wakari.io/sharing/bundle/rsignell/ndbc_group_test)
   *  examining groups, variables, and time series plot using pandas
*  [ADCIRC](http://adcirc.org) / [Model Testing] (https://www.wakari.io/sharing/bundle/rsignell/ADCIRC_water_level_and_velocity_3d)
    *  using NetCDF4-Python library to access velocity data from a triangular grid ocean model via OPeNDAP, specifying the desired URL, time, layer and lat/lon region of interest
*  [Access data in Wakari from the OPeNDAP Web Service using NetCDF4-Python](https://www.wakari.io/sharing/bundle/rsignell/opendap_bathy_test)
    *  using NetCDF4-Python, pandas, creating plot 
*  [Testing CF Conventions on an SJROFS Ocean Forecast Model](https://www.wakari.io/sharing/bundle/rsignell/SJROFS)
    * using [CF Conventions](http://cf-pcmdi.llnl.gov) in the context of [St. John's River Operational Forecast System (SJROFS)](http://tidesandcurrents.noaa.gov/ofs/sjofs/sjofs.html)
*  [Plotting Argo Data and Glider Data from Australia's Integrated Marine Observing System (IMOS)](https://www.wakari.io/sharing/bundle/rsignell/IMOS_Demos)
    *  using netCDF, python, matplotlib
*  [Reading NCEP ADP Global Upper Air and Surface Weather Observations (PREPBUFR format)](https://www.wakari.io/sharing/bundle/rsignell/gdas2csv)
    *  uses netCDF, pandas (including writing to csv)
*  [Examining Longitude and Latitude Extent in Directory Access Protocol endpoint (GLOS)](https://www.wakari.io/sharing/bundle/rsignell/glos_range)
*  [Extract and plot data from a NetCDF file or OPeNDAP dataset](https://www.wakari.io/sharing/bundle/rsignell/NetCDF_plot)
*  [Using pyugrid to examine netCDF4 Dataset](https://www.wakari.io/sharing/bundle/rsignell/pyugrid_test)
    *  uses [pyugrid](https://github.com/pyugrid/pyugrid), a Python API to utilize data written using the unstructured grid [UGRID conventions](https://github.com/ugrid-conventions/ugrid-conventions), as well as matplotlib.tri to plot a contour amp

###[ERDDAP](http://coastwatch.pfeg.noaa.gov/erddap/index.html)
*  [Examining and Plotting GTS Data from ERDDAP](https://www.wakari.io/sharing/bundle/rsignell/ERDDAP_GTS_Test)
   *  Using [REST Requests](http://rest.elkstein.org/2008/02/what-is-rest.html), pandas, read_csv

###SciTool Python Packages for Cartography
*  [Examining a Regional Ocean Model Using Iris](https://www.wakari.io/sharing/bundle/rsignell/iris_z_coords)
    *  uses [Iris](http://esc24.github.io/iris/index.html) 
*  [Examining Cartopy Visualization Tools](https://www.wakari.io/sharing/bundle/rsignell/cartopy)
    *  uses [Cartopy](http://scitools.org.uk/cartopy/index.html)
*  [Using Iris to Access Data from U.S. IOOS Regional and Federal Models](https://www.wakari.io/sharing/bundle/rsignell/scitools)
    *  uses Iris, time_near, var_lev_date, myplot, USGS/COASWST, MARACOOS/ESPRESSO, SECOORA/NCSU, CENCOOS/UCSC, HIOOS, Global RTOFS/NCEP 

###Testing IOOS/Regional Services
*  [IOOS 52 North SOS](http://ioossos.axiomalaska.com) / [Pyoos Testing Notebook](https://www.wakari.io/sharing/bundle/rsignell/pyoos_axiom)
    *  uses [pyoos](https://pypi.python.org/pypi/pyoos), a Python library for collecting Met/Ocean observations, to test and examine a particular IOOS service
*  [Accessing IOOS Coastal Ocean Modeling Testbed (COMT)](https://www.wakari.io/sharing/bundle/rsignell/ADCIRC_water_level_and_velocity)
    *  examining [Western North Atlantic, Caribbean and Gulf of Mexico Tidal Databases](http://adcirc.org/products/adcirc-tidal-databases/)
    *  using netCDF4, pandas, matplotlib, pylab, date time to plot water depth against water velocity vectors on a map and create a time series of water levels at a particular location
*  [Accessing Northeastern Coastal Ocean Forecast System using the NetCDF4-Python](https://www.wakari.io/sharing/bundle/rsignell/NECOFS_water_levels)
    *  examining [NECOFS](http://www.neracoos.org/datatools/forecast/oceanforecasts)
    *  using netCDF4, pandas, read_csv to examine water level at particular stations according to the model by finding (x,y) coordinates near desired station locations and then plotting these water levels on a time series graph
*  [Accessing an IOOS approved web service using python](https://www.wakari.io/sharing/bundle/rsignell/pyoos)
    *  using pandas, cStringIO, [pyoos](https://pypi.python.org/pypi/pyoos), read_csv and CoopsSos
*  [Accessing New England Coastal Ocean Forecast System via OPeNDAP](https://www.wakari.io/sharing/bundle/rsignell/FVCOM_depth_and_velocity)
    *  using  pylab, matplotlib.tri, netCDF4
    *  examining the [New England Coastal Ocean Forecast System](http://fvcom.smast.umassd.edu/research_projects/NECOFS/) and [THREDDS Data Server](http://www.smast.umassd.edu:8080/thredds/forecasts.html?dataset=gom2_nocache)
*  [Extracting time series from NWS NOAA/NCEP Wavewatch III](https://www.wakari.io/sharing/bundle/rsignell/cf_3d_to_1d)
    *  using [NWS NOAA/NCEP Wavewatch III](http://polar.ncep.noaa.gov/waves/wavewatch/wavewatch.shtml), pandas, datetime
    *  provides an example of extracting and plotting a 3D time series
*  [Access CSW to determine ServiceType](https://www.wakari.io/sharing/bundle/rsignell/Model_search)
    *  accessing NODC, NGDC, and DATA.NOAA.GOV, using CSW, netCDF4 to access model data
*  [Accessing CSW with OWSLib using ISO queryables](https://www.wakari.io/sharing/bundle/rsignell/CATALOG.DATA.GOV-CSW-DAP)
    *  using pylab, owslib.csw, netCDF4, pandas, datetime
*  [Using regional data and independent CSV data to approach marine Conflict Resolution Planning](https://www.wakari.io/sharing/bundle/rsignell/Right_Whale_Sightings)
    *  uses pandas, netCDF4, read_csv, group.to_csv, and demonstrating how to use matplotlib to create histograms of the data and then group the data by month on maps of bathymetry
    *  this notebook was created as an approach to resolving conflicts between aquaculture siting and Right Whale protection in Cape Cod Bay
*  [Accessing IOOS Coastal Ocean Modeling Testbed (COMT)](https://www.wakari.io/sharing/bundle/rsignell/IKE_water_levels)
    *  using [COMT](http://www.ioos.noaa.gov/modeling/testbed.html), CSW, pandas, matplotlib.tri, netCDF4, datetime, pyugrid
    *  demonstrates finding nearby points of interest from a model and harvesting service url's from a CSW endpoint
    *  demonstrates time series plotting different outputs of water levels from a plot over a certain time period

###Comparing Data Catalogues
*  [Comparing NOAA Geoportal to Data.Gov](https://www.wakari.io/sharing/bundle/rsignell/NODC_and_Data.gov)
    *  using CSW to compare NODC geoportal to data.gov
*  [Comparing model results from NODC and NGDC](https://www.wakari.io/sharing/bundle/rsignell/Model_check)
    *  using CSW, ServiceType, [OPenDAP](http://docs.opendap.org/index.php/QuickStart)
*  [Accessing CSW metadata for particular variable, bounding box and visualization](https://www.wakari.io/sharing/bundle/rsignell/DATA.NOAA.GOV-CSW-DAP)
    *  using pylab, owslib.csw, netCDF4, pandas, datetime
    *  includes list of CSWs
*  [Accessing ncSOS with OWSLib and Pyoos](https://www.wakari.io/sharing/bundle/rsignell/ncSOS_and_OWSlib_and_pyoos)
    *  using [NcSOS](https://github.com/asascience-open/ncSOS), which adds an OGC SOS service to datasets in THREDDS server and complies with [IOOS SWE Milestone 1.0](https://code.google.com/p/ioostech/source/browse/#svn%2Ftrunk%2Ftemplates%2FMilestone1.0) templates
    *  using pandas, owlsib.etree, pdb, oslib.sos, datetime
*  [Using CSW to search for datasets with a certain variable in a certain bounding box and determining Service endpoints](https://www.wakari.io/sharing/bundle/rsignell/CSW_Testing_ISO_Queryables-USGS)
    *  using [ISO Queryables](http://essi-lab.eu/do/view/GIcat/CSWISO-Ext-Queryables) (these are incredibly valuable in terms of determining a set of records that can be accessed through particular Services (WCS, WMS, WFS, SOS)), netCDF4, pandas