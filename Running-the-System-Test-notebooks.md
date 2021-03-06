We recommend using the Anaconda python environment.  If you use anaconda, you should be able to create a system-test environment using the conda-requirements.txt file found in each system-test directory.

First clone the system-test repo:
```
git clone git@github.com:ioos/system-test.git
```
and navigate to the subdirectory that contains the system-test notebook you want to run.   In that subdirectory, you should find a `conda-requirements.txt` file.  For example:
```
cd system-test/Theme_2_Extreme_Events/Scenario_2A/Extremes_Waves
```
you should see a notebook file ending in `.ipynb` as well as a `conda-requirements.txt` file.

First add rsignell's binstar repo which contains many of the binary packages used in they system test:
```
conda config --add channels https://conda.binstar.org/rsignell
```
* If you are NOT using Wakari,  you should be able to be able to create a new custom environment that only installs the packages in use the requirements file.  
```
conda create -n systest --file conda-requirements.txt
source activate systest
```
and then use the `systest` environment to run the notebook.

* If you are using Wakari, creating a new environment doesn't seem to work, so you can add the packages an existing environment.  For example, go to `Terminals`, choose `Shell` and `np18py27-1.9` and click on `+Tab` to open a terminal with the `np18py27-1.9` environment.   Then type

```
conda config --add channels https://conda.binstar.org/rsignell
conda install --file conda-requirements.txt
``` 
and then use the `np18py27-1.9` environment to run the notebook. 

