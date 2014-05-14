Environments in wakari depend on the channel URLs that are accessible.  You can make sure that the right channels are accessible via a command shell using a "conda info" command.  
After entering conda info, you should see the following output:
 
`[~]$ conda info`
`Current conda install:`
                                                                                                                                                                     `platform : linux-64`

`conda version : 3.4.1`

`python version : 2.7.6.final.0`

`root environment : /opt/anaconda  (writable)`

`default environment : /opt/anaconda/envs/np18py27-1.9`

`envs directories : /opt/anaconda/envs`

`package cache : /opt/anaconda/pkgs`

``channel URLs : https://conda.binstar.org/wakari1/linux-64/``
                        ``https://conda.binstar.org/r/linux-64/``
                        ``http://conda.binstar.org/rsignell/linux-64/``
                        ``http://repo.continuum.io/pkgs/free/linux-64/``
                        ``http://repo.continuum.io/pkgs/pro/linux-64/``
`config file : /user_home/w_hdean/.condarc`
`is foreign system : False`



You should be able to do:
conda install pyoos
also
(don't need to include the -c rsignell now, since that's in your list of channels automagically searched)
don't forget to restart kernel after any package installs