# Project introduction 
This is a clean, minimal template repository for starting new Python projects in SCC's remote desktop, with sensible defaults for structure, environment setup and packaging. This template has a suggested project structure, it has 3 main directories:
- **Data**: This is where all your data for analysis will/should be stored.
- **Notebooks**: This is where all your Python/R notebooks for analysis should be stored.
- **Setup**: This folder holds all the files related to python setup and snowflake integration.

> ⚠️ Note - Please do no rename or move (change location) of the 'Setup' folder and any files within the folder. 
<br>

# Virtual environment:
Is is always recommended to use a virtual environment in any analytical product.
This allows another person to replicate, review, contribute to, and run your project using the same underlying code packages.


## Setup directory explained
This directory contains all the files you need for python setup and integration with Snowflake.
1.  It contains a powershell script file i.e. 'setup-env.ps1', which is core set-up file, it:
   - Checks for virtual environment at ```.\.venv```
      - If one is found. it is activated.
      - If not found, one is created, then activated.
   - Checks for ```snee-packages.txt``` and attempts installation. See below for details.
   - Checks for ```requirements.txt``` and prompts the user to install the packages within, if it is present.

In Vscode, on the left-hand tab, click "Explorer" and then click on ```setup-env.ps1```. Execute this powershell script. At the top right of the powershell file click the play button to do this.


2. It also contains 'connection.toml' file : This information in this file is used to integrate snowflake and use dataset stored in snowflake directly in VS code.
> ⚠️ Note - Please update the 'user' field in the file with your username/email.


## SNEE Packages
By default, this installs SNEE_utils package when you run the setup-env.ps1 file :

- SNEE Utils, a python package which formats matplotlib/seaborn/plotly plots with the SNEE IF theme/guidelines and provides helper functions to establish a connection and save data from Snowflake Database.
  -  [SNEE Utils](https://github.com/SNEE-ICS/SNEE_Utils.git)


# Explaining the files
1. ```.gitignore```        --> This is a plain text file that tells Git which files or directories to ignore, meaning they wont be tracked, committed or pushed
2. ```README.md```         --> Readme file for the repository (Not related to python setup). The contents of this file will be displayd on GITEA repository page
3. ``` connection.toml```  --> toml file to establish connection with snowflake.
4. ```requirements.txt```  --> This file is used to list and download the basic Python packages your project would depends on.
5. ```setup-env.ps1```     --> This file is the main setup file. It has 3 important steps
   - Check for Virtual environment: if found then skip else create new VE (.venv) and activate it.
   - Check for any repositories you want to load from snee-packages.txt file (by default it has SNEE-IF stylings and python functions, you can add on your)
   - Download all the Python packages from requirements.txt file
6. ```snee-packages.txt``` --> This file lists all the repositories/packages we want to load from Gitea.
7. ```example_analysis.ipynb``` --> This is an example fiel on how to establish connection with snowflake and load data from sql, load data from a file and SNEE plotting themes.

<hr>
