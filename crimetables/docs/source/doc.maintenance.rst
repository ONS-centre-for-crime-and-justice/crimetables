.. _doc.adding_tables:

***********
Maintenance
***********

This section covers how to update and re-run the NoC pipeline if you are running 
it on a new set of data. The pipeline has been designed so that there should be as 
little manual intervention as possible and if there does need to be manual intervention 
it is limited to a set number of scripts.

------------------------------------------------------------------------

File Paths
==========

If you are just trying to re-run the pipeline on new data, the only thing that will 
need updating is the scripts that create the individual crime type datasets.

* You will need to run off the new years as CSVs and put all years you want read in 
  into a folder and re-direct the function to read in this specific function.
  
* You will also need to update the 'financial_year' variable label so that the current 
  year has a label and does not have a missing value. This is important as lots of the 
  functions pick up the financial year variable so not updating this will mean the 
  pipeline will fall over
  
* You may also need to update where the outputs are going to be saved. This can be 
  done in all of the **run_(crime_type)** files and is straightforward to update.
  


Titles and footnotes
====================

Adding and amending footnotes is likely to be the part of the process that will need 
the most manual intervention. This is because things always change with new data and 
footnotes are the best way of conveying that to our users. Titles will obviously need 
updating due to year references changing.

* This is straightforward as each individual table has an accompanying footnotes 
  script. Any changes to specific tables should be made to the individual footnote 
  scripts.
