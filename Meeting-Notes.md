# DMAC IT Testing Status Meeting Notes
30 May 2014
## Attendees
•	For ASA:  Kelly Knee, Andy Bird, David Foster, Bob Fratantonio
•	For Axiom:  Will Koeppen, Kyle Wilcox
•	For USGS: Rich Signell
•	For LMI/IOOS:  John Kupiec
## Topics
### How to Organize Various Notebooks
The discussion included several topics.  One topic was whether Python notebooks that are related to the same scenario should be merged into one notebook as testing progresses.  The decision was to keep notebooks separate, enabling a modular approach in which a given notebook could be used to test the same functionality across various scenarios and themes.  The second topic was, given that notebooks will remain separate and be used in modular fashion, how should they be organized under the test scenarios and larger test themes. Kyle Wilcox offered to enhance the directory tree structure under which notebooks are currently organized.  The directory tree will have three levels:
*  Test Theme
*  Test Scenario
*  Notebook
Additionally the notebooks should be given descriptive names that do not include the original developer's name.
### How to Document a Test
This discussion proceeded from an earlier discussion between Rich Signell and Derrick Snowden over how best to document a test procedure and its results.  Derrick had suggested to Rich that tests should be documented either within a wiki or within Python notebooks.    Rich attempted these approaches and found drawbacks to each.  He settled on using a GitHub issue to document test results including summary of successes, issues, etc.  He showed the group and example of this approach, and noted its advantages:
*  Unlike a Python notebook or a wiki, GitHub enables a tester to draw and drop images and graphics. This approach is much easier and quicker than the alternative of copying and pasting a link within a notebook or on a wiki page.  
*  The image displays within the GitHub issue.  A reader does not have to click on a link to see an image.
*  Formatting is easier within a GitHub issue than within a Google document…at least for Rich….
*  A GitHub issue title can include the name of the notebook that was run and the run date.
*  Unlike a wiki page or a Python notebook, a GitHub issue can have a discussion thread.

Rich demonstrated that searching for test results within GitHub is easy when an appropriate label is supplied.  Rich suggested the label “Progress,” and no other attendee had a better suggestion.  “Progress” it is.

Further discussion centered on how to enable traceability between a particular test report issue within GitHub and the associated Python notebook. Andy suggested embedding the issues within the notebook as an HTML frame; the link would be to an associated test report issue within GitHub.    Andy’s suggestion was adopted.

### Configuration Management of Notebooks
There were several minutes of discussion on the appropriate configuration protocols to use so that different developers could work on their own notebooks and commit them at the appropriate time without overwriting similar efforts by other developers.  In other words, the discussion chewed on questions always encountered when using Git for configuration management.  Such questions included, but were not limited to:
•	Should each developer clone a complete copy of the code base and work on it independently?
•	Do different versions of a given notebook constitute branches or forks?
•	Should different developers work within designated branches to keep their work separate?
•	Can the team implement a continuous build process?
To the best of this scribe’s knowledge, only one decision was made: for the immediate future, individual pull requests will not be merged.  At some future point, one of the developers who are skilled in GitHub may merge the pull requests.  The issues associated with using Git to manage configuration need to be discussed further.  
### Iris
Iris is currently not working on Python notebooks running off the OSX platforms. Rich said that he would troubleshoot this issue by using a build from NYU.  Kyle said that he would assist Rich in this effort.  Rich also said that he would attempt to confirm that Iris works on Anaconda.  Rich stressed that it is reasonable for members of the scientific community to expect that Python notebooks would run successfully within Anaconda, since Anaconda is a subset of Python that is customized for use in scientific analyses.
### Weekly Taskings
There was a general request for some way to document the essential elements of an Agile stand-up for each team.  Rich suggested using GitHub Markdown to compile stand-up information for each status meeting.  Rich’s suggestion was received tepidly. An alternative would be for each team to document their stand-up elements within the How You Can Contribute wiki page.  There was not much enthusiasm for this alternative.  The need for each team to document their agile stand-up lists (Accomplishments, Underway, and Issues) remains, but is unresolved.





