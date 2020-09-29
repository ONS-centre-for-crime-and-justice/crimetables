.. _doc.troubleshooting:

**************************
Errors and Troubleshooting
**************************

This section covers common errors that occur in the pipeline and fixes. It also 
covers some advice on how to start troubleshooting errors with the pipeline and 
functions. 

------------------------------------------------------------------------

Common Errors
=============


* Key Error - variable(1.0)
  
  This error usually means there is an issue with the mapping file. Typically your 
  function is trying to apply a table label but the variable and value label are 
  not in the lookup file.
  
  Double check the lookup file.
  
* Footnotes not assigned

  This error occurs when you try and output your tables but actually occurs when 
  you run your table outputs through GPTables. You have included footnotes that do 
  not have a reference in the actual table.
  
  To fix this you will need to have a in table reference for each footnote. This 
  involves adding $$x$$ around your footnote number. This will let GPTables know 
  that this is a footnote reference.  
  
* Indexing error

  This error occurs when manipulating dataframes in Python but the index columns 
  are not consistent. This is an easy fix you will just need to reset your index 
  using the following code::
  
  `df.reset_index(inplace=True)`
  
* G Drive issue

  Before running the pipeline you will need to ensure that you have access to the
  G: drive (CrimeStatistics). If this is offline the pipeline will not run. 
  
  .. image:: filepath_error.jpg
  


Troubleshooting
===============

This section covers some places to start when you are having problems with your code

**i'm thinking about all the things we got wrong so please chip in!!**

General Script
^^^^^^^^^^^^^^

* Double check that all the variables you needa re on the dataset and have been 
  read in correctly.
  
* Ensure your scripts are flowing through and correwctly calling the dataframes 
  you think they are. For example ensure you are calling the filtered df not the 
  original.
  
* Ensure that the bases look reasonable. If your bases do not look right then the 
  estimates will becalculated using the wrong people/cases.
  
Functions
^^^^^^^^^

* Insert print statements into your functions to identify what your function is 
  doing at each stage. This is a good way to identify if it is doing what you think 
  it should be doing.
  
* Double check all the parameters you have enetered for your function. It may be 
  that not all parameters are in the right format or you are picking up the wrong 
  parameters all together.
  