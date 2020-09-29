.. _Setup:

*********
Setup
*********

This section covers all the initial setup needed to run the NoC pipeline.
This includes Python, Pip and GitLab. You may need to register service desk requests
for some of this software.

------------------------------------------------------------------------

Setting up Artifactory
======================

Artifactory is a software package repository (you might see this abbreviated to “repo” on developer websites). 
Open source tools like R and Python rely on a community of developers to provide 
functionality and add-ons for the basic tools. These add-ons are made available 
via a central website as packages or modules that can be installed when needed.  
 
When you install these tools at home, they usually work directly with the online 
community web repositories. However, this could result in security vulnerabilities. 
It’s unlikely, but somebody might be able to inject malicious code into an R or 
Python package and load it into the main repository. 

For this reason, ONS has created replicas of the main software repositories that 
our open source tools use. These repositories are hosted by us on the Artifactory 
platform, and rigorously scanned for security vulnerabilities. That way, we can 
be sure that whatever we install is low risk. 

When you use R or Python in ONS, instead of pulling packages down from the online 
repositories, you use Artifactory to obtain what you need instead. To be able to 
do that, you need to set it up to work with your machine.


Accessing your ONS artifactory ‘user:key’ information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Install ONS `Artifactory <http://art-p-01/artifactory/webapp/#/login>`_
   You need to log a Service desk call following:
   *I want something > Software, Applications & Platforms > Product Support (Rational, GitLab, Jenkins, Artifactory) > 
   Submit with following completed fields*
   
   .. image:: servicedesk.jpg
   
   For additional help and guidance please use the `JFrog Artifactory User Guide <https://ons.service-now.com/nav_to.do?uri=%2Fkb_view_customer.do%3Fsysparm_article%3DKB0010090>`_

2. Log into your Artifactory account at `ONS Artifactory <http://art-p-01/artifactory/webapp/#/login>`_
   Click your username in top right-hand corner. 
   Note: your username is the same as your Windows log in and is also your ‘user’ input in the ‘user:key’ information.
   Unlock your User Profile by entering your password and clicking ‘Unlock’
   When you have unlocked this, you will now have access to your Encrypted Password.
   Press the clipboard and it will copy your password ready to be pasted.

Setting up Anaconda
===================

Anaconda is a management platform for Python (it can also be used to install R, but we don’t need to go there). 
Anaconda provides a set of tools to develop Python code (like the Spyder IDE) 
and access Python packages using Artifactory. 

Once again, we need to configure Anaconda to point to Artifactory, so it knows 
where to look for Python packages. This step is needed to link you Anaconda software 
to your ONS Artifactory in order to access packages.

Adding your ONS artifactory user
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Locate your *.condarc* file. This can be found in 

   *C: Users/(your username)/.condarc.*
   
   If this file is here, skip to step 4.
   
2. If you cannot see that file, locate the template file from the `Installation Guidance <//FA1RVWAPXX333/Crime Statistics/Crime RAP project/Installation guidance>`_ folder.

3. 	Copy the template .condarc folder from the Installation guidance folder and paste into this area:

    *C: Users/(your username)/.condarc.*
    
    Right click on the file and select open with – Notepad (you may need to select a program to open with from a pop up box)
    
    You will then need to edit the file to add in your ‘user:key’ information in the relevant places
    
    .. image:: condarc.jpg


Once you have added your information, save and close the file. This step of installation is complete.

Setting up Pip
==============

Pip (it stands for Pip Installs Packages) is a package manager and installer for 
Python. With PIP, you can install other Python packages and any additional add-ons 
they require to work. Pip works inside the Anaconda environment, but you need to 
install it before you can use it, and you need to set it up so it works properly 
with ONS network security.  To do that, we write a Windows initialization file 
(these are the ones with .ini extensions) that pip looks for and reads on startup.

Adding your ONS artifactory ‘user:key’ information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This step is needed to set up PIP so it knows where to look for Python packages.

1. Open windows file explorer.

2. In the file path area type: 
   
   *%appdata%*
   
   This is a short cut to take you to the relevant folder where your ‘pip’ file is located:
   (FYI appdata is a Windows variable, and %appdata% means “the value of appdata” - 
   it just points to C:/Users/<your_Windows_username/AppData/Roaming)
   
   In this area you should see a folder called ‘pip’. If you see this folder, skip to step 5. 
   
3. Create a new folder in the ‘Roaming’ area called ‘pip’
   
4. Copy the template ‘pip.ini’ file from the Installation Guidance folder and paste this into the new ‘pip’ folder you have created.

5. Open the ‘pip.ini’ file within the pip folder in Notepad. (If this doesn’t open in Notepad automatically, 
   you will need to right click, open with and then select the program)

   You will then need to edit the file to add in your ‘user:key’ information in the relevant place:
   
   .. image:: pip_ini.jpg
   
   Once you have added your information, save and close the file. This is step of installation is complete.


Setting up Git
==============

GIT is a version control and auditing system for software development.  It was 
invented by Linus Torvalds, the man who wrote the Linux operating system. Git 
provides tools that record who changed what, why and when as you develop a software 
package, and is very widely used. Git works alongside a web repository 
(at ONS this is GitLab, but you may already have seen GitHub online) which records 
all the changes everybody in the team makes and provides some extra tools for 
collaboration. GIT is the most important piece of software you’re going to be using. 
Before you can start changing software (this usually involves breaking it – don’t worry, that is normal), 
you need to set up your details so that when you make a change, Git and GitLab 
know who you are and are sure about that. For full instructions on getting started 
with GIT please see this link: 

`Installing Git <file://fa1rvwapxx333/Crime%20Statistics/Crime%20RAP%20project/Installation%20guidance/Intro_to_git.html>`_


Crimetables Installation
========================

Crimetables is the python package that has been developed by the python working 
group to enable CSEW data to be analysed within python. It contains a set of 
functions that all do different things from reading in data to actual analysis 
of data.

There are two ways of downloading the crimetables package depending on how you 
want to use it: 

Method 1: For analysis and amending the package
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This method is for those who are undertaking new work within the team and would need to 
develop their own functions, and such want to make those functions available to all crimetables users. 

1. You will need to set up on Gitlab and have an active account. This can be set 
   up through the ServiceDesk.

2. You will then need to be added to the crimetables repository. This is where 
   all development of the crimetables takes place. You will need to be confident 
   with using GIT for developing this package.

3. In anaconda prompt navigate to the folder where you want to clone the crimetables
   package. Do this by using #: to move drive and cd ### to move between folders.

4. Once you are a member of the crimetables repository you can then clone the 
   repository to your chosen location on your laptop.

5. Once you have a version of crimetables cloned to your laptop you will then need 
   to tell python where to look for this package when it is being called in scripts. 
   To do this you need to navigate to the crimetables folder and use:
   
   `pip install -e .`
   
6. Crimetables is now ready to use! 

Method 2: For analysis only
^^^^^^^^^^^^^^^^^^^^^^^^^^^
This method is for those who are only interested in running pre-existing 
functions/pipelines. This will not enable you to make changes to the crimetables 
package that can be uploaded to Git.

1. In the anaconda prompt you can install a package without downloading it to your laptop.

   `pip install git+https://github.com/ONS-centre-for-crime-and-justice/nature-of-crime-python.git`

Coding Tips
===========

Here is a link to all the training courses currently run by ONS: 

`Training Courses <https://learninghub.ons.gov.uk/totara/dashboard/index.php?id=6>`_
