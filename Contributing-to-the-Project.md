# Creating or updating notebooks
1.  Generation of `.py` files along side the `.ipynb` files.  You can generate the `.py` files in **one** of two ways:
  1.  Run `ipython notebook --script`.  This will save a .py file every time the notebook is saved.
  2.  Add the line `c.FileNotebookManager.save_script = True` to your `ipython_notebook_config.py` file and restart the notebook. 
  3.  After you are done editing your notebook, `cd` to the directory the `.ipynb` file is in and run `ipython nbconvert --to python [your_notebook_file]`
2.  Organization of "helper' libraries.  Each scenario folder should contain a single file called `utilities.py`.  Keep all helper functions in here.  Use this utilities option to help keep the notebooks readable.  When importing from `utilities.py`, please use specific imports like `from .utilities import my_cool_function, my_method`.  Please do **not** do: `from .utilities import *`.
3.  Installation requirements.  To assist in someone being able to replicate the work of the system-test, we need to start documenting the specifics on how to setup each scenario notebook.  In each scenario folder, please start creating a `README.md` file containing information about the scenario, what its intentions are, and how to set it up to run.  I've included some examples in this PR for existing scenarios.  Bonus points if the documentation covers using both `conda` and `pip`.
4.  Commit the `.ipynb` files with **ALL** cells successfully run.  If you can't run the entire notebook, don't commit it!
5.  Avoid using ipython notebook magic, aka `%pylab` and `%matplotlib`
6.  Adhere to the folder structure this PR lays out:
```bash
|---- Theme_[theme number]_[theme name]
|     |---- Scenario_[theme number][scenario letter]_[scenario title]
|     |     |---- README.md
|     |     |---- utilities.py
|     |     |---- Scenario_[theme number][scenario letter]_[some unique term].py
|     |     |---- Scenario_[theme number][scenario letter]_[some unique term].ipynb
````

 
# Testing and Merging Pull Requests
1. Make sure your local branch is up to date.  

2. Create a new branch in your local repo named after the target you're testing. e.g. in the case of @Bobfrat 's recent PR #77 

`git branch waves_notebook`
`git checkout waves_notebook`

3. Merge from Bobfrat:waves_notebook into your local copy of ioos:waves_notebook

`git pull https://github.com/Bobfrat/system-test.git waves_notebook`

4. Now it is `waves_notebook` 

5. Test how you see fit but at least verify that the output is visible in the *,ipynb and that the *.py is generated.  Also test to see that the README.md has been updated to include any new issues/bugs etc discovered during the development of the notebook.

6. Figure out how to merge   (Little help here @daf, @kwilcox, @bueller)


# Documenting Issues
Recall from the [project plan](https://github.com/ioos/system-test/wiki/Project-Management-Plan#goals-and-objectives) that one of the primary objectives of this project is to list all fixes and enhancements that are identified during the test.  These fixes are to be prioritized and **only some of them** will actually be implemented during the course of the test.  However, we must document all of them.  It isn't an exaggeration to say that the list of bugs/enhancements are arguably more important than the collection of functioning notebooks.  The project time is short and we need to be very judicious when choosing whether to spend time fixing bugs.  Most often the answer is to log it and move on, potentially to another notebook. So, what exactly are bugs, and how do we log them.

## What types of bugs do we expect?
The answer here is really anything but at least includes:
* I tried to use client X to plot data and it didn't understand my data type.
* I searched for dataset Y in catalog Z and couldn't find it.  I know dataset Y exists so it needs to be published via a service and/or registered in one or more catalogs.
* Dataset Y is available here but the service sucks because...
   * no metadata
   * no aggregation
   * server times out when I ask for more that NN days worth of data.
* This data set is published as a bunch of ascii files and not a standards compliant service.  Please publish.
* I found all of these great records in this catalog but none of them actually point to data published online.

etc.  You get the idea, these are not just issues with software crashing but also include failure to follow procedures.

## How do I log issues?
At the very least all issues should be logged on the system-test issue tracker.  In some cases the issue is actually related to a software bug and the software package exists in another github repository.  For these cases, log the issue on the appropriate repo so that the development team is aware and can factor it in to their plans.  Also, log it in the system-test repo and just include a pointer to the real issue.  The purpose for doing this is to create a record that will get included in the final report from the system-test project.

TODO: outline the tagging/labeling scheme.

Additionally, for each notebook, there is a README.md file which includes a description of the notebook and the details of any dependencies.  Issues should be written up in a section of the README that describes the disposition of the issue currently.  Consider this section a storyline describing what was learned in the course of creating the notebook.  

@rsignell-usgs has some additional thoughts on documenting the things learned from creating the inundation notebook.