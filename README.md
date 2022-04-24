﻿# Highway-Health README

## Description

Highway Health will use data from APIs supplied by the following company's APIs: OpenWeatherMaps, Here Real-Time Traffic, Twitter. The data gathered from those APIs will be utilitized to create a map visualization via Deck.gl. This project supports an end user that requires knowledge of the status of roads, such as shipping and trucking companies. 


## Requirements

Python 3.10

MySQL or MariaDB SQL Database for local database usage

PIP [Optional, to install Python dependencies]

## Server Install instructions

1. Download Project.
2. Run `pip install -r requirements.txt` to install the required dependencies.

3. To run the server, use `python /flaskr/__init__.py`
4. Visit the server on `http://localhost:5000` or `127.0.0.1:5000`

#### Sitemap
[url] / - homepage (displays traffic and weather information as plot points)

[url] / graph - 3d hexagonal bar graph (displays traffic information as elevated bars)

[url] / heatmap - heatmap (displays traffic information on a heatmap)


## Database Install instructions

1. Download Project.
2. Run ```npm install <package_name>``` to install the following dependencies: 
    1. webpack-cli@3.3.2 --save-dev
    2. #deck.gl/core #deck.gl/layers
3. Before running the script, change MYSQL server variables [host, user, password, database],
    - Edit the script using Text Editor of your choice
4. Commands to run:

#### First time setup:

* Run `python initCreateDB.py` to create the local database and table(s).
* Run `python datasetManip.py` to insert all .geojson data into local database (this will take some time).
* Run `npm start` within the source directory (development) to start the ?????

* Schedule the scripts to get hourly API calls: 

* On Windows, create a batch file and use the Windows Scheduler to run the API calls on an hourly basis. 
    1. For the batch file, open notepad and enter the file locations for python.exe and the python script you wish to run. 
    2. This should look like: `"C:\ ... \Python\python.exe" "C:\Users\...FolderName\pythonScript.py"`
    3. Then save as `yourfilename.bat`
    4. Open the Task Scheduler application (this is in the Windows Administrative Tools). 
    5. Select "Create Task." Give it a Name, Select Action -> Start a Program and select the .bat file you created, then set a Trigger that will run the .bat file hourly.
    6. Select Finish, and your hourly task will be scheduled. 
* On Linux/Mac, schedule with a cronjob.
    1. Add instructions when i have time...this is temporary

## Additional Requirements

--- Functional Requirements ---

1. API access
   - OpenWeatherMaps for weather + geodata.
   - Twitter for keyword and geodata trends.
   - Here for real-time traffic data and map features.
2. Deck.gl
   - Webpack.
   - One of the base maps (currently testing with Leaflet).
   - Website application to be written in Javascript with CSS for style.
3. Data processing
   - Via regular API calls (frequency to be determined) from all three data sources (OpenWeatherMaps, Here, and Twitter) a larger data source will be 
  compiled and then manipulated to identify/confirm traffic or weather related concerns that can cause hazardous highways in the United States. 
   - Data manipulation to be complete via Python (most likely and within the JavaScript used for Deck.gl listed in point 2).
4. Workspace that allows development in Python, Javascript, CSS (any others to be determined).
5. Access to the Highway Health Github Repository required for version control.


--- External Interface Requirements ---

1. For the user: 
   - Hardware: Access to computer, internet
   - Software: Access to an interet browser
2. For the developer/owner: 
   - APIs referenced in point 1 in Functional Requirements will need to be able to communicate with the code used to implement our Deck.gl map application.


--- Nonfunctional Requirements ---

1. Performance
   - Will leave as is for now until tests are run on APIs to see what kind of performance we can expect. 
2. Quality
   - Need to have: have data from all sources marked on the map based on our internal requirements (to be determined after API testing) within a certain 
  geographic range (to be determined once feasibility is tested). Essentially: Place a dot on the map. 
   - Nice to have: Add functionality to "a dot on the map" to have things like: different colored dots based on severity, tooltips showing the issue (flooding, 
  traffic, so on), etc.
  
  
--- Data Manipulation and Catagorization ---

   - Once tested what we can use from data pulled via APIs can go back to this and determine what to include/exclude from map and how we want to catagorize what 
  we do put on the map.

