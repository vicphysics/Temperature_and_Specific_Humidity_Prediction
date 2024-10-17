Data will be gathered from several sources. Here is a list of these sources:

NSRDB 

HADISDH (Humidity data) 

NCEI/NOAA 

ONI

# NSRDB:

National Renewable Energy Laboratory (NREL): National Solar Radiation Database (NSRDB)
The NSRDB is provided in annual .h5 files and currently spans 1998-2018 with data files stored in Hierarchical Data Format Version 5 (HDF5).
Each year can be accessed from /nrel/nsrdb/nsrdb_${year}.h5
The data is provided from Amazon Web Services (AWS) using the HDF Group's Highly Scalable Data Service (HSDS).

NSRDB archived data sets for 1961-1990 for 237 locations and from 1991-2005 for 1,454 locations in the United States and its territories are also available in CSV format from

https://nsrdb.nrel.gov/data-sets/archives

Instructions for setting up h5pyd can be found at:

https://github.com/NREL/hsds-examples/blob/master/notebooks/03_NSRDB_introduction.ipynb

Information on installing HSDS can be found here:

https://github.com/HDFGroup/hsds

h5pyd package only works for Python 3.8-3.10. Users running Python 3.11 or later have reported problems. 

Refer to https://forum.hdfgroup.org/t/error-using-hsds-to-download-nsrdb-data/11840/

Open up Anaconda Powershell Prompt Window and type commands below:

Create the virtual environment:

    python -m venv myenv

Activate the virtual environment:

    .\myenv\Scripts\activate

Downgrade to Python 3.10 to use h5pyd:
    
    conda install python==3.10

Check version:
    
    python --version

Install h5pyd:
    
    pip install --user h5pyd

Install hsds:
    
    pip install hsds

Then configure HSDS using HSDS app command:
    
    hsconfigure   

At the prompt, enter:
    
    hs_endpoint = https://developer.nrel.gov/api/hsds
    hs_username = None
    hs_password = None
    hs_api_key = phTY324bPYr6d6ECVsZhFMlmjw1fZDCG6q0Q48IF
   
This API key was created specifically for V.Sciortino5865@o365.ncu.edu for use in this research.

To get your own API key, visit https://developer.nrel.gov/signup/

To generate a requirements.txt file to list all dependencies, use:
    
    pip freeze > requirements.txt

Make the following adjustments to requirements.txt:
    
    aiobotocore==2.5.0
    cryptography==41
    ipython==7.6.0
    jedi==0.17.2
    numpy==1.26.4
    urllib3==2.2.2

Install needed package:
    
    pip install tensorflow-io-gcs-filesystem

You can also add the above contents to a configuration file at ~/.hscfg or have hsconfigure create this file for you.

This latter option was used with a file created and placed in directory:
    
    C:/Users/User/        
    
(This path is the working directory for Anaconda and holds all Jupyter notebooks)

# The following code in Jupyter Notebook creates the virtual environment and incorporates all dependencies:

#Create the virtual environment
    
    !python -m venv myenv

#Activate the virtual environment
    
    !.\myenv\Scripts\activate

#Downgrade to Python 3.10 to use h5pyd
    
    !conda install python==3.8

#Check version
    
    !python --version

#Update dependencies
    
    !pip install -r requirements.txt

#Install missing package dependency
    
    !pip install tensorflow-io-gcs-filesystem
    
    !pip install --user h5pyd

#Install hsds using:
    
    !pip install hsds

# HADISDH (Humidity data):

The Met Office humidity data (HADISDH) datasets are stored in NetCDF or Network Common Data Form (.NC) geospatial file format. 
To access and visualize this data in Python, the required libraries are discussed with application python code at:

https://medium.com/analytics-vidhya/how-to-read-and-visualize-netcdf-nc-geospatial-files-using-python-6c2ac8907c7c

# NCEI/NOAA (National Oceanic and Atmospheric Administration):



# Ocean Oscillations Niño Index (ONI):

