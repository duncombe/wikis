[Theme 1: Baseline Assessment](#theme1)  
[Theme 2: Extreme Events](#theme2)  
[Theme 3: Species Protection & Marine Habitat Conservation](#theme3)  

#####Notebook Format:
*  **Theme Title**
   * **Scenario Description and Title**
       *  _**Questions**_
         *  DISCOVERY Process (code and narrative)
         *  ACCESS Process (code and narrative)
         *  USE Process (code and narrative)
    *  _**Results and Conclusions**_ (narrative)
*  Title Scheme for Notebooks: (Theme Number).(Scenario Letter).(Question Number)

<a name="theme1"/>
### Theme 1: Baseline Assessment
The Baseline Assessment theme will compile basic summary statistics for each catalog that will be used in the other science themes.  For example, how many records are loaded in each CSW?  For each record, assess whether or not service endpoints are present and [identifiable using standard vocabularies](https://github.com/OSGeo/Cat-Interop).

1. Count the records in each CSW: Theme1.ScenarioA.csw_count.ipynb
2. Summarize the usage of service endpoint identifiers: Theme1.ScenarioA.service_identifiers.ipynb
3. Vocabulary related summaries
   * Presence absence of CF Standard names
   * Presence/absence of IOOS core variables, IOOS Vocab at MMI, SWEET terms, BODC P02 terms

*  [Examining CSW Endpoints](http://nbviewer.ipython.org/gist/emiliom/7459209) (Emilio Mayorga, 11/15/2013)
*  [Baseline Assessment of Web Services](https://www.wakari.io/sharing/bundle/hdean/Test%20Catalogs%20for%20WMS%20Layers)
*  [Assessment of Model Records](https://www.wakari.io/sharing/bundle/hdean/Test%20Catalogs%20for%20Model%20Outputs)
*  [Assessing Catalogs for inclusion of Agency Records](https://www.wakari.io/sharing/bundle/hdean/Theme%201_Baseline_Federal%20Agency%20Metrics)

<a name="theme2"/>
### Theme 2: Extreme Events 
#### Scenario A: Severe Coastal Storm

Model - Data Comparison Notebooks:
   *  [Inundation Notebook](http://nbviewer.ipython.org/urls/raw.githubusercontent.com/rsignell-usgs/notebook/fef9438303b49a923024892db1ef3115e34d8271/CSW/IOOS_inundation.ipynb?create=1) - to compare observed and modeled water levels

* Waves Notebook - to compare observed and modeled wave parameters

* Winds Notebook - to compare observed and modeled wind speeds and directions

* Currents Notebook - to compare observed (HFRADAR) and modeled currents

Extreme Value Analyses:
*  [Water level Extremes Notebook](http://nbviewer.ipython.org/github/ioos/system-test/blob/master/theme2_extreme_events/ioos_extreme_events_water_level.ipynb)

* [Wave Extremes Notebook](http://nbviewer.ipython.org/github/ioos/system-test/blob/master/theme2_extreme_events/ioos_extreme_events_waves.ipynb) - to discover whether sufficient record lengths exist for calculating return periods for wave parameters

* Wind Extremes Notebook - to discover whether sufficient record lengths exist for calculating return periods for wave parameters

* Currents Extremes Notebooks - to discover whether sufficient record lengths exist for calculating return periods for wave parameters

Overland Flooding:

* Storm Surge Measurements - Can we discover data from  USGS storm tide sensors and rapid deployment gages and map locations and water levels


#### Scenario B: Oil Tanker Spill
#####Question 1: Can we discover and access the core variables applicable to analysis of an Oil Tanker Spill from the available list of Registries?
*  [Notebook 2.B.1](https://www.wakari.io/sharing/bundle/hdean/Theme%202_Scenario%20B_Oil%20Tanker%20Spill_Web%20Services%20Count-Copy0)

#### Scenario C: Search & Rescue - Commercial Aircraft Crash

<a name="theme3"/>
### Theme 3: Species Protection & Marine Habitat Conservation
*  [Assessing Seabird Vulnerability in the Bering Sea](https://www.wakari.io/sharing/bundle/hdean/Theme%203,%20Scenario%20-%20Assessing%20Seabird%20Vulnerability%20in%20the%20Bering%20Sea)

#### Scenario A:  Assessing Chesapeake Bay Biology
#### Scenario B:  Assessing the Quality of Baleen Whale Summer Feeding Grounds Off the New England Coast
#### Scenario C:  Planning for Wind Turbine Sites using Ecosystem Base Approach
#### Scenario D:  Mineral Extraction