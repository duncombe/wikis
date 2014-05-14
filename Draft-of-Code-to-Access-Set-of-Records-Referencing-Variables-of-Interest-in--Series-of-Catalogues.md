###Cell 1:
```python
import pandas as pd
from pandas import Series, DataFrame
import numpy as np
from numpy import random
import matplotlib.pyplot as plt
import matplotlib.cbook as cbook
import csv
import re
import cStringIO
import urllib2
import parser
import pdb
import json
import random
import datetime as dt
from datetime import datetime
from pylab import *
from owslib.csw import CatalogueServiceWeb
from owslib.wms import WebMapService
from owslib.csw import CatalogueServiceWeb
from owslib.sos import SensorObservationService
from owslib.etree import etree
from owslib import fes
import netCDF4
import SPARQLWrapper
from SPARQLWrapper import SPARQLWrapper, JSON
from SPARQLWrapper import SPARQLWrapper2
from zipfile import ZipFile
import xml.sax, xml.sax.handler
```

###Cell 2:
####This Cell will contain all of your lists that you will access throughout this code.
```python 
endpoints = ['http://www.nodc.noaa.gov/geoportal/csw',
             'http://www.ngdc.noaa.gov/geoportal/csw',
             'http://catalog.data.gov/csw-all',
             'http://cwic.csiss.gmu.edu/cwicv1/discovery',
             'http://geoport.whoi.edu/geoportal/csw',
             'https://edg.epa.gov/metadata/csw',
             'http://cmgds.marine.usgs.gov/geonetwork/srv/en/csw',
             'http://cida.usgs.gov/gdp/geonetwork/srv/en/csw',
             'http://geodiscover.cgdi.ca/wes/serviceManagerCSW/csw', 
             'http://geoport.whoi.edu/gi-cat/services/cswiso']
var_key = [**Inside this bracket enter in a Comma Separated List of Variables of Interest**]
```

###Cell 3:
####This cell compiles a list of variables based on your list that might be included in IOOS catalogs in different formats utilizing SPARQLWrapper, and prints out that final list.
```python
sparql = SPARQLWrapper("http://mmisw.org/sparql")

Q = []
RecVars = []
for K in var_key:
    A = """
PREFIX ioos: <http://mmisw.org/ont/ioos/parameter/>
SELECT DISTINCT ?parameter ?definition ?unit ?property ?value 
WHERE {?parameter a ioos:Parameter .
       ?parameter ?property ?value .
       ?parameter ioos:Term ?term . 
       ?parameter ioos:Definition ?definition . 
       ?parameter ioos:Units ?unit .
       FILTER (regex(str(?property), "(exactMatch|closeMatch)", "i") && regex(str(?value), """ + '"'+K+'"' +', "i") )'   
    B = """
      } 
ORDER BY ?parameter
"""
    queryStringLoop = A+B
    sparql.setQuery(queryStringLoop)
    sparql.setReturnFormat(JSON)
    j = sparql.query().convert()
    Q.append(j)
    for jt in j:
        j["head"]["vars"]
        k = j['results']
        k1 = k['bindings']
        for k in k1:
            k2 = k['value']
            k3 = k2['value']
            k4 = k3[34:]
            k4list = k4.encode('ascii') 
            RecVars.append(k4list)
            
RecVarsMerg = RecVars + var_key
print RecVarsMerg
```
###Cell 4:
####This Cell prints out records and titles for your list of variables available via the first three endpoints.  If you would like to see the output for all endpoints or a different number of endpoints, simply replace the number on the first line "For endpoint in endpoints[:3]:"

variables1 = []
records1 = []
titles1 = []
lenrecords1 = []
lentitles1 = []

for endpoint in endpoints[:3]:
    csw = CatalogueServiceWeb(endpoint,timeout=60)
    for v in RecVarsMerg[:2]:
        try:
            csw.getrecords(keywords = [v], maxrecords = 60, esn = 'full')
            records1.append(csw.results)
        except Exception, ex1:
            records1.append('Error')
        try:
            for rec in csw.records:    
                titles1.append(csw.records[rec].title)
        except Exception, ex1:
            titles1.append('Error') 
    lentitles1.append(len(titles1[-1]))
    lenrecords1.append(len(records1[-1]))

zipvar1 = zip(endpoints, records1,lenrecords1, titles1,lentitles1)
df = DataFrame(data = zipvar1, columns = ['endpoints','records1','lenrecords1', 'titles1','lentitles1'])
df.head()