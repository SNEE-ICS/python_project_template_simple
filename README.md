# Project introduction 
This is a clean, minimal template reporitoy for starting new Python projects in AXYM --with sensible defaults for structure, environment setup and packaging.
Automatically creates/detects a virtual environment, installs SNEE python packages and requirements.txt file. This has a suggested project structure.


# Virtual environment:
Is is always recommended to use a virtual environment in Axym or in any analytical product.
This allows another person to replicate, review, contribute to, and run your project using the same underlying code packages.


## Setup script
This package contains a powershell script. This is multifunctional.
1. Checks for virtual environment at ```.\.venv```
   1. If one is found. it is activated.
   2. If not found, one is created, then activated.

2. Checks for ```snee-packages.txt``` and attempts installation. See below for details.
3. Checks for ```requirements.txt``` and prompts the user to install the packages within, if it is present.

In Vscode, on the left-hand tab, click "Explorer" and then click on ```setup-env.ps1```. Execute this powershell script. At the top right of the powershell file click the play button to do this.

## SNEE Packages
By default, this contains :
- SNEETools, a python package currently containing functionality for SQL queries and notebook publishing.
  -  [https://git.apps.axym.co.uk/snee.SNEE_ICS/AxymPyTools]
- SNEEStyle, a python package which formats matplotlib / seaborn plots with the SNEE IF theme/guidelines.
  -  https://git.apps.axym.co.uk/snee.SNEE_ICS/SNEEstyle


# Explaining the files
1. ```.gitignore```        --> This is a plain text file that tells Git which files or folders to ignore, meaning they wont be tracked, committed or pushed
2. ```README.md```         --> Readme file for the repository (Not related to python setup). The contents of this file will be displayd on GITEA repository page
3. ```requirements.txt```  --> This file is used to list and download the basic Python packages your project would depends on.
4. ```setup-env.ps1```     --> This file is the main setup file. It has 3 important steps
   1. Check for Virtual environment: if found then skip else create new VE (.venv) and activate it.
   2. Check for any repositories you want to load from snee-packages.txt file (by default it has SNEE-IF stylings and python functions, you can add on your)
   3. Download all the Python packages from requirements.txt file
5. ```snee-packages.txt``` --> This file lists all the repositories/packages we want to load from Gitea.
6. ```Data```              --> This folder will have example data (GP_lookup.xlsx), or data output we get after running the SQL's.
7. ```Notebooks```         --> This folder should have all the Python/R notebooks for analysis.
8. ```SQL```               --> This folder is to store all the SQL scripts.

<hr>