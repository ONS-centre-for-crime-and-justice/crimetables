.. _doc.adding_tables:

*************
Adding Tables
*************

This section covers how to amend the current NoC pipeline to incorporate either 
a new type of table, so a new 'nature', or a whole new suite of tables, a new crime 
type for example.

------------------------------------------------------------------------

Adding a new offence
====================

There may be a situation where it is decided a new crime type is being added into 
the NoC tables. There is a set process for how to incorporate this new crime type 
into the pipeline to minimise the effect this new addition will have on the existing 
code. 

1. The first step is to develop the new offence type tables independently of the 
   existing pipeline. An example of this can be found in the first picture of the 
   pipeline section of this documentation.
   
2. Once the suite of tables has been created independently it should be checked 
   thoroughly to ensure that the outputs are as expected and each script is running 
   smoothly.
   
3. Now we can start incorporating it into the pipeline. You will need to create a 
   CSV file for that crime type that contains all the variables needed and have all 
   the scripts call that reduced data.
   
4. Once all your new tables have been run through GPTables you will need to bring 
   them all together into a **run_(crime_type)** file. This will call each GPTables 
   object and output them as a complete excel workbook.
   
5. The last step is to incorporate your new **run_(crime_type)** file into the 
   **run_pipeline** file. This will mean that all the NoC tables can be run as 
   part of this script.


Adding a new table type
=======================

Adding a new table type is slightly differen to adding a new crime type. You need to 
amend the existing pipeline to pick up this new table type for the different crime 
types you are including this tables for.

1. The first step again is to independently create this new table type independent 
   from the existing pipeline

2. Once you are happy the new table is created it needs to be checked thoroughly to 
   ensure you are getting accurate numbers and it does not throw any errors.
   
3. Now we can incorporate it into the pipeline. The first step to this is to add 
   the new variables to that crime type specific dataset so the new table can be 
   run off using that dataset.
   
4. Once the table is created and been run through GPTables to apply formatting 
   and footnotes you will then need to amend the **run_(crime_type)** file for the 
   specific crime type you are applying this new table to so it picks up the new table 
   and outputs it with the rest of that crime type in a workbook.
