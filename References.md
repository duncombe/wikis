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

###[ERDDAP](http://coastwatch.pfeg.noaa.gov/erddap/index.html)
*  [Examining and Plotting GTS Data from ERDDAP](https://www.wakari.io/sharing/bundle/rsignell/ERDDAP_GTS_Test)
   *  Using [REST Requests](http://rest.elkstein.org/2008/02/what-is-rest.html), pandas, read_csv

###[Iris](http://esc24.github.io/iris/index.html) 
(easy to use, and community-driven Python library for analysing and visualising meteorological and oceanographic data sets)
*  [Examining a Regional Ocean Model Using Iris](https://www.wakari.io/sharing/bundle/rsignell/iris_z_coords)

###Testing IOOS Services
*  [IOOS 52 North SOS](http://ioossos.axiomalaska.com) / [Pyoos Testing Notebook](https://www.wakari.io/sharing/bundle/rsignell/pyoos_axiom)
    *  uses [pyoos](https://pypi.python.org/pypi/pyoos), a Python library for collecting Met/Ocean observations, to test and examine a particular IOOS service