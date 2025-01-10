Data will be gathered from several sources. Here is a list of these sources:

HADISDH (Humidity data) 

NSRDB (solar radiation output data)

NCEI/NOAA (exogenous variables)

WDC-SILSO (solar activity data)

ONI (exogenous variable)

# HADISDH (Humidity data):

Powershell Code Instructions for Setting Up Virtual Environment (myenv):
1)	Install Anaconda Navigator 2.6.3 via download from https://www.anaconda.com/download 
2)	Open Anaconda Navigator and select the “Environments” tab
3)	Click “Create” at the bottom of the screen and enter
a.	Name: myenv
b.	Check box next to “Python”
c.	Select version 3.10.16 from dropdown box
d.	Click “Create” button
4)	Select the new environment “myenv” and press the play button to open terminal

Check versions being used using:
python --version
conda --version
pip --version

Note: Versions used were: conda version 24.11.2, python version 3.10.16, pip version 24.2. We are using C:\Users\User as our working directory which contains the Anaconda3 folder. 

At first prompt, enter:
pip install netCDF4

At next prompt, enter:
pip install h5pyd

Then at next prompt, enter:
pip install hsds

To confirm installation location of h5pyd package, at the prompt, enter:
pip show h5pyd | findstr "Location:"

Our location is: C:\users\user\appdata\roaming\python\python310\site-packages

At next prompt, enter:
python C:\Users\User\AppData\Roaming\Python\Python310\site-packages\h5pyd\_apps\ hsconfigure.py
There are four options that will come up one at a time. Set these to: 
hs_endpoint = https://developer.nrel.gov/api/hsds
hs_username = None
hs_password = None
hs_api_key = phTY324bPYr6d6ECVsZhFMlmjw1fZDCG6q0Q48IF
	
This API key was created specifically for V.Sciortino5865@o365.ncu.edu for use in this research. To get your own API key, visit https://developer.nrel.gov/signup/

Change directory (if needed) to use jupyter notebooks:
cd C:\Users\User

At prompt, enter to open and start using jupyter notebooks to run Python code:
jupyter notebook


Instructions for setting up h5pyd can be found at:
https://github.com/NREL/hsds-examples/blob/master/notebooks/03_NSRDB_introduction.ipynb

Information on installing HSDS can be found here:
https://github.com/HDFGroup/hsds


The Met Office humidity data (HADISDH) datasets are stored in NetCDF or Network Common Data Form (.NC) geospatial file format. 
To access and visualize this data in Python, the required libraries are discussed with applicable python code at:

https://medium.com/analytics-vidhya/how-to-read-and-visualize-netcdf-nc-geospatial-files-using-python-6c2ac8907c7c

Download the following files from HADISDH website:

| HADISDH Source File Names |
| :-: |
WMO_000000-029999_humidity.tar
WMO_030000-049999_humidity.tar
WMO_050000-079999_humidity.tar
WMO_080000-099999_humidity.tar
WMO_100000-149999_humidity.tar
WMO_150000-199999_humidity.tar
WMO_200000-249999_humidity.tar
WMO_250000-299999_humidity.tar
WMO_300000-349999_humidity.tar
WMO_350000-399999_humidity.tar
WMO_400000-449999_humidity.tar
WMO_450000-499999_humidity.tar
WMO_500000-549999_humidity.tar
WMO_550000-599999_humidity.tar
WMO_600000-649999_humidity.tar
WMO_650000-699999_humidity.tar
WMO_700000-709999_humidity.tar
WMO_710000-714999_humidity.tar
WMO_715000-719999_humidity.tar
WMO_720000-721999_humidity.tar
WMO_722000-722999_humidity.tar
WMO_723000-723999_humidity.tar
WMO_724000-724999_humidity.tar
WMO_725000-725999_humidity.tar
WMO_726000-726999_humidity.tar
WMO_727000-729999_humidity.tar
WMO_730000-799999_humidity.tar
WMO_800000-849999_humidity.tar
WMO_850000-899999_humidity.tar
WMO_900000-949999_humidity.tar
WMO_950000-999999_humidity.tar

We use the code from the Extract NC files followed by the Python code to choose NC Files to generate the list of files below.

HADISDH Files chosen to be used in study:

Region 1:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 7962 | 44.381 | -106.72 | hadisd.3.4.1.202411p_19310101-20241201_726654-94054_humidity.nc |
| 7987 | 42.727 | -114.455 | hadisd.3.4.1.202411p_19310101-20241201_726816-04110_humidity.nc |
| 7999 | 45.196 | -123.134 | hadisd.3.4.1.202411p_19310101-20241201_726881-94273_humidity.nc |
| 8000 | 45.826 | -119.261 | hadisd.3.4.1.202411p_19310101-20241201_726883-04113_humidity.nc |
| 8120 | 48.461 | -119.521 | hadisd.3.4.1.202411p_19310101-20241201_727890-94197_humidity.nc |
| 8133 | 47.923 | -122.283 | hadisd.3.4.1.202411p_19310101-20241201_727937-24222_humidity.nc |

Region 2:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 6994 | 32.259 | -107.721 | hadisd.3.4.1.202411p_19310101-20241201_722725-23078_humidity.nc |
| 7032 | 33.976 | -117.625 | hadisd.3.4.1.202411p_19310101-20241201_722899-03179_humidity.nc |
| 7239 | 36.311 | -119.623 | hadisd.3.4.1.202411p_19310101-20241201_723898-53119_humidity.nc |
| 7424 | 40.044 | -107.888 | hadisd.3.4.1.202411p_19310101-20241201_724674-94050_humidity.nc |
| 7426 | 39.23 | -106.871 | hadisd.3.4.1.202411p_19310101-20241201_724676-93073_humidity.nc |
| 7463 | 36.212 | -115.194 | hadisd.3.4.1.202411p_19310101-20241201_724846-53123_humidity.nc |
| 7482 | 38.504 | -122.811 | hadisd.3.4.1.202411p_19310101-20241201_724957-23213_humidity.nc |
| 8184 | 36.985 | -120.111 | hadisd.3.4.1.202411p_19310101-20241201_745046-93242_humidity.nc |
| 8186 | 33.038 | -116.916 | hadisd.3.4.1.202411p_19310101-20241201_745056-53120_humidity.nc |

Region 3:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 7671 | 41.99 | -93.619 | hadisd.3.4.1.202411p_19310101-20241201_725472-94989_humidity.nc |
| 7704 | 41.763 | -96.18 | hadisd.3.4.1.202411p_19310101-20241201_725527-94978_humidity.nc |
| 7861 | 46.547 | -90.918 | hadisd.3.4.1.202411p_19310101-20241201_726419-94929_humidity.nc |
| 7870 | 43.156 | -90.678 | hadisd.3.4.1.202411p_19310101-20241201_726438-94994_humidity.nc |
| 7892 | 43.168 | -95.21 | hadisd.3.4.1.202411p_19310101-20241201_726500-14972_humidity.nc |
| 7906 | 43.026 | -102.52 | hadisd.3.4.1.202411p_19310101-20241201_726517-94039_humidity.nc |
| 7907 | 43.389 | -99.843 | hadisd.3.4.1.202411p_19310101-20241201_726518-94990_humidity.nc |
| 7938 | 44.638 | -90.188 | hadisd.3.4.1.202411p_19310101-20241201_726574-94985_humidity.nc |
| 7979 | 46.352 | -104.261 | hadisd.3.4.1.202411p_19310101-20241201_726777-94055_humidity.nc |
| 8083 | 46.011 | -102.652 | hadisd.3.4.1.202411p_19310101-20241201_727584-94038_humidity.nc |

Region 4:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 6501 | 33.636 | -91.756 | hadisd.3.4.1.202411p_19310101-20241201_720175-53919_humidity.nc |
| 6541 | 38.958 | -94.371 | hadisd.3.4.1.202411p_19310101-20241201_720306-53879_humidity.nc |
| 6668 | 35.14 | -90.236 | hadisd.3.4.1.202411p_19310101-20241201_722054-53959_humidity.nc |
| 6697 | 36.682 | -101.505 | hadisd.3.4.1.202411p_19310101-20241201_722095-03030_humidity.nc |
| 6844 | 30.029 | -91.885 | hadisd.3.4.1.202411p_19310101-20241201_722314-53915_humidity.nc |
| 6854 | 30.344 | -89.822 | hadisd.3.4.1.202411p_19310101-20241201_722330-53865_humidity.nc |
| 6870 | 32.338 | -90.221 | hadisd.3.4.1.202411p_19310101-20241201_722354-13927_humidity.nc |
| 6891 | 30.068 | -95.556 | hadisd.3.4.1.202411p_19310101-20241201_722429-53910_humidity.nc |
| 6895 | 30.361	| -95.418 | hadisd.3.4.1.202411p_19310101-20241201_722444-53902_humidity.nc |
| 6899 | 30.744	| -95.587 | hadisd.3.4.1.202411p_19310101-20241201_722447-53903_humidity.nc |
| 6901 | 32.032	| -96.399 | hadisd.3.4.1.202411p_19310101-20241201_722469-53912_humidity.nc |
| 6909 | 32.713	| -96.269 | hadisd.3.4.1.202411p_19310101-20241201_722489-53911_humidity.nc |
| 6929 | 33.183	| -96.59 | hadisd.3.4.1.202411p_19310101-20241201_722541-53914_humidity.nc |
| 6950 | 33.209	| -97.199 | hadisd.3.4.1.202411p_19310101-20241201_722589-03991_humidity.nc |
| 6963 | 30.912	| -102.917 | hadisd.3.4.1.202411p_19310101-20241201_722618-23091_humidity.nc |
| 6969 | 31.925	| -102.387 | hadisd.3.4.1.202411p_19310101-20241201_722648-03031_humidity.nc |
| 7131 | 36.77	| -90.322 | hadisd.3.4.1.202411p_19310101-20241201_723300-03975_humidity.nc |
| 7152 | 35.257	| -93.095 | hadisd.3.4.1.202411p_19310101-20241201_723429-53920_humidity.nc |
| 7155 | 36.29	| -94.312 | hadisd.3.4.1.202411p_19310101-20241201_723436-53922_humidity.nc |
| 7156 | 36.371 | -92.472 | hadisd.3.4.1.202411p_19310101-20241201_723439-53918_humidity.nc |
| 7182 | 35.541	| -97.647 | hadisd.3.4.1.202411p_19310101-20241201_723544-03954_humidity.nc |
| 7193 | 34.558	| -98.417 | hadisd.3.4.1.202411p_19310101-20241201_723575-03950_humidity.nc |
| 7202 | 35.695	| -101.396 | hadisd.3.4.1.202411p_19310101-20241201_723635-03024_humidity.nc |
| 7347 | 38.93	| -90.433 | hadisd.3.4.1.202411p_19310101-20241201_724347-53904_humidity.nc |
| 7361 | 39.845	| -89.684 | hadisd.3.4.1.202411p_19310101-20241201_724390-93822_humidity.nc |
| 7414 | 38.072	| -102.687 | hadisd.3.4.1.202411p_19310101-20241201_724636-03013_humidity.nc |
| 7423 | 39.228	| -106.316 | hadisd.3.4.1.202411p_19310101-20241201_724673-93009_humidity.nc |
| 7432 | 39.241	| -102.282 | hadisd.3.4.1.202411p_19310101-20241201_724689-03026_humidity.nc |
| 7599 | 38.564 | -90.149 | hadisd.3.4.1.202411p_19310101-20241201_725314-03960_humidity.nc |
| 9858 | 36.118 | -97.091 | hadisd.3.4.1.202411p_19310101-20241201_999999-53926_humidity.nc |

Region 5:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 6744 | 41.351	| -71.806 | hadisd.3.4.1.202411p_19310101-20241201_722151-14794_humidity.nc
| 7287 | 40.876	| -74.283 | hadisd.3.4.1.202411p_19310101-20241201_724094-54743_humidity.nc
| 7329 | 41.563	| -83.477 | hadisd.3.4.1.202411p_19310101-20241201_724287-04848_humidity.nc
| 7489 | 40.821	| -72.867 | hadisd.3.4.1.202411p_19310101-20241201_725016-54790_humidity.nc
| 7528 | 41.626	| -80.212 | hadisd.3.4.1.202411p_19310101-20241201_725104-04843_humidity.nc
| 7538 | 41.046	| -78.411 | hadisd.3.4.1.202411p_19310101-20241201_725119-54792_humidity.nc
| 7549 | 43.35 | -76.383 | hadisd.3.4.1.202411p_19310101-20241201_725146-54773_humidity.nc
| 7553 | 42.108	| -77.984 | hadisd.3.4.1.202411p_19310101-20241201_725157-54757_humidity.nc
| 7555 | 40.65 | -75.448 | hadisd.3.4.1.202411p_19310101-20241201_725170-14737_humidity.nc
| 7562 | 42.644	| -77.053 | hadisd.3.4.1.202411p_19310101-20241201_725194-54778_humidity.nc
| 7571 | 41.346	| -82.179 | hadisd.3.4.1.202411p_19310101-20241201_725214-04849_humidity.nc
| 7573 | 40.873	| -81.889 | hadisd.3.4.1.202411p_19310101-20241201_725216-04842_humidity.nc
| 7585 | 41.336	| -84.429 | hadisd.3.4.1.202411p_19310101-20241201_725254-04851_humidity.nc
| 7606 | 41.454	| -86.998 | hadisd.3.4.1.202411p_19310101-20241201_725327-04846_humidity.nc
| 7622 | 42.224	| -83.74 | hadisd.3.4.1.202411p_19310101-20241201_725374-94889_humidity.nc
| 7652 | 41.137	| -75.377 | hadisd.3.4.1.202411p_19310101-20241201_725434-54789_humidity.nc
| 7786 | 43.279	| -70.924 | hadisd.3.4.1.202411p_19310101-20241201_726056-54791_humidity.nc
| 7805 | 42.807	| -72.001 | hadisd.3.4.1.202411p_19310101-20241201_726163-54770_humidity.nc
| 7816 | 44.933	| -74.848 | hadisd.3.4.1.202411p_19310101-20241201_726223-94725_humidity.nc
| 7838 | 45.072	| -83.565 | hadisd.3.4.1.202411p_19310101-20241201_726390-94849_humidity.nc
| 7862 | 42.759	| -87.818 | hadisd.3.4.1.202411p_19310101-20241201_726424-94818_humidity.nc
| 7863 | 43.775	| -87.849 | hadisd.3.4.1.202411p_19310101-20241201_726425-04841_humidity.nc
| 8034 | 45.813 | -88.113 | hadisd.3.4.1.202411p_19310101-20241201_727437-94893_humidity.nc

Region 6:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 6640 | 28.474	| -82.454 | hadisd.3.4.1.202411p_19310101-20241201_722014-12818_humidity.nc
| 6678 | 30.393	| -86.467 | hadisd.3.4.1.202411p_19310101-20241201_722069-53853_humidity.nc
| 6687 | 32.899	| -80.041 | hadisd.3.4.1.202411p_19310101-20241201_722080-13880_humidity.nc
| 6714 | 27.913	| -82.686 | hadisd.3.4.1.202411p_19310101-20241201_722116-12873_humidity.nc
| 6772 | 34.272	| -83.83 | hadisd.3.4.1.202411p_19310101-20241201_722185-53838_humidity.nc
| 6783 | 33.354	| -84.569 | hadisd.3.4.1.202411p_19310101-20241201_722197-53819_humidity.nc
| 6840 | 33.178	| -86.782 | hadisd.3.4.1.202411p_19310101-20241201_722300-53864_humidity.nc
| 7057 | 34.733	| -76.657 | hadisd.3.4.1.202411p_19310101-20241201_723037-93765_humidity.nc
| 7094 | 34.984	| -81.056 | hadisd.3.4.1.202411p_19310101-20241201_723117-53871_humidity.nc
| 7095 | 34.672	| -82.881 | hadisd.3.4.1.202411p_19310101-20241201_723118-53850_humidity.nc
| 7100 | 34.254	| -82.153 | hadisd.3.4.1.202411p_19310101-20241201_723124-53874_humidity.nc
| 7108 | 35.197	| -81.156 | hadisd.3.4.1.202411p_19310101-20241201_723147-53870_humidity.nc
| 7116 | 36.048	| -79.474 | hadisd.3.4.1.202411p_19310101-20241201_723174-93783_humidity.nc
| 7119 | 35.015	| -80.624 | hadisd.3.4.1.202411p_19310101-20241201_723194-53872_humidity.nc
| 7139 | 36.48 | -82.399 | hadisd.3.4.1.202411p_19310101-20241201_723350-13877_humidity.nc
| 7280 | 39.873	| -75.227 | hadisd.3.4.1.202411p_19310101-20241201_724080-13739_humidity.nc
| 7286 | 38.69 | -75.362 | hadisd.3.4.1.202411p_19310101-20241201_724093-13764_humidity.nc
| 7311 | 39.044	| -84.672 | hadisd.3.4.1.202411p_19310101-20241201_724210-93814_humidity.nc
| 7321 | 38.365	| -82.555 | hadisd.3.4.1.202411p_19310101-20241201_724250-03860_humidity.nc
| 7350 | 39.585	| -85.8	| hadisd.3.4.1.202411p_19310101-20241201_724356-53866_humidity.nc
| 7354 | 39.143	| -86.617 | hadisd.3.4.1.202411p_19310101-20241201_724375-03893_humidity.nc
| 7357 | 39.825	| -86.296 | hadisd.3.4.1.202411p_19310101-20241201_724384-53842_humidity.nc
| 7531 | 40.238	| -75.555 | hadisd.3.4.1.202411p_19310101-20241201_725109-54782_humidity.nc
| 7533 | 40.33 | -75.123 | hadisd.3.4.1.202411p_19310101-20241201_725113-54786_humidity.nc
| 7534 | 39.919	| -76.877 | hadisd.3.4.1.202411p_19310101-20241201_725114-93778_humidity.nc
| 7574 | 39.361	| -84.521 | hadisd.3.4.1.202411p_19310101-20241201_725217-53855_humidity.nc
| 7575 | 40.47 | -81.422 | hadisd.3.4.1.202411p_19310101-20241201_725224-04852_humidity.nc
| 7603 | 39.474	| -88.272 | hadisd.3.4.1.202411p_19310101-20241201_725317-53802_humidity.nc
| 8247 | 30.337	| -81.513 | hadisd.3.4.1.202411p_19310101-20241201_747820-53860_humidity.nc
| 8248 | 26.079	| -80.162 | hadisd.3.4.1.202411p_19310101-20241201_747830-12849_humidity.nc

HADISDH Location Information:
Note: For files where "Water within 10 km" is blank, the water/land variable will be zero (0=land). Otherwise, it will be set to one (1=near water).

| File | Location Name | State | Water within 10 km (using Google Earth's Measure Tool)|
| :-: | :-: | :-: | --- |
| 6640 | American Aviation Flight Academy | FL | Sparkman Lake |
| 6668 | West Memphis Municipal Airport | AR | Mississippi River |
| 6678 | Destin Executive Airport (DTS) | FL | Gulf of Mexico |
| 6687 | Charleston International Airport | SC | Ashley River, Goose Creek Reservoir |
| 6697 | Guymon Municipal Airport | OK | Sunset Lake |
| 6714 | St. Pete-Clearwater International Airport | FL | Tampa Bay |
| 6744 | Westerly State Airport | RI | Atlantic Ocean |
| 6772 | Lee Gilmer Memorial Airport | GA | Lake Lanier |
| 6783 | Atlanta Regional Airport-Falcon Field | GA | Lake McIntosh |
| 6840 | Shelby County Airport | AL | Ebenezer Swamp |
| 6844 | Acadiana Regional Airport (KARA) | LA | Spanish Lake |
| 6854 | Slidell Municipal Airport KASD | LA | Bayou Bonfouca, Lake Pontchartrain |
| 6870 | Hawkins Field Airport | MS | Mayes Lake, Pearl River |
| 6891 | David Wayne Hooks Memorial Airport | TX |  |
| 6895 | Conroe-North Houston Regional Airport | TX |  |	 
| 6899 | Huntsville Municipal Airport | TX | Spring Lake, Club Lake |
| 6901 | Corsicana Municipal Airport | TX | Richland-Chambers Reservoir |
| 6909 | Terrell Municipal Airport | TX | New Terrell City Lake |
| 6929 | McKinney National Airport | TX | East Fork Trinity River |
| 6950 | Denton Enterprise Airport | TX | Hickory Creek, Pecan Creek |
| 6963 | Fort Stockton Aviation | TX |  |
| 6969 | Odessa-Schlemeyer Field Airport | TX |  |	 
| 6994 | Deming City Airport | NM |  |
| 7032 | Chino Airport | CA | Chino Creek |
| 7057 | Michael J. Smith Field | NC | Newport River, Harlowe Creek |
| 7094 | Rock Hill-York County Airport | SC | Lake Wylie |
| 7095 | Oconee County Regional Airport-CEU | SC | Lake Keowee |
| 7100 | Greenwood County Airport | SC | Saluda River |
| 7108 | Gastonia Municipal Airport | NC |  |	 
| 7116 | Burlington Alamance Regional Airport | NC | Lake Mackintosh, Beaver Creek |
| 7119 | Charlotte-Monroe Executive Airport | NC | Baker Quarry Lake, Crooked Creek |
| 7131 | Poplar Bluff Municipal Airport | MO | Black River |
| 7139 | Tri-Cities Airport | TN | Boone Lake |
| 7152 | Russellville Municipal Airport-Rue | AR | Arkansas River |
| 7155 | Northwest Arkansas National Airport | AR | Little Osage Creek, Cave Springs |
| 7156 | Baxter County Airport | AR | Howard Creek |
| 7182 | Wiley Post Airport-PWA | OK | Lake Hefner, Lake Overholser |
| 7193 | Lawton-Fort Sill Regional Airport | OK | Wolf Creek |
| 7202 | Hutchinson County Airport | TX | Pantex Reservoir, Canadien Creek |
| 7239 | Hanford Municipal Airport | CA |  |
| 7280 | Philadelphia International Airport | PA | Delaware River |
| 7286 | Delaware Coastal Airport | DE | Deep Creek |
| 7287 | Essex County Airport | NJ | Passaic River |
| 7311 | Cincinnati/Northern Kentucky Int’l Airport | KY | Ohio River |
| 7321 | Huntington Tri-State Airport | WV | Ohio River |
| 7329 | Toledo Executive Airport | OH | Henry Creek, Crane Creek |
| 7347 | St. Charles County Regional Airport | MO | Mississippi River |
| 7350 | Shelbyville Municipal Airport | IN | Big Blue River |
| 7354 | Monroe County Airport | IN |  |
| 7357 | Eagle Creek Airpark | IN | Eagle Creek Reservoir |
| 7361 | Abraham Lincoln Capital Airport | IL | Sangamon River |
| 7414 | Southeast Colorado Regional Airport | CO | Arkansas River |
| 7423 | Leadville-Lake County Regional Airport | CO | Turquoise Lake |
| 7424 | Meeker Airport | CO | White River |
| 7426 | Aspen/Pitkin County Airport | CO | Woody Creek |
| 7432 | Kit Carson County Airport-ITR | CO |  |
| 7463 | North Las Vegas Airport | NV |  |	 
| 7482 | Charles M. Schulz-Sonoma County Airport | CA | Lake Benoist |
| 7489 | Long Island Skydiving Center | NY | West Millpond, East Millpond |
| 7528 | Port Meadville Airport	| PA | Conneaut Lake |
| 7531 | Heritage Field Airport | PA | Schuylkill River |
| 7533 | Doylestown Airport | PA | Peace Valley Reservoir |
| 7534 | York Airport | PA | Lake Pahagaco, Little Conewaqo Creek |
| 7538 | Clearfield-Lawrence Township Airport | PA | West Branch Susuehanna River |
| 7549 | Oswego County Airport | NY | Oswego River |
| 7553 | Wellsville Municipal Airport | NY |  |	 
| 7555 | Lehigh Valley International Airport | PA | Lehigh River |
| 7562 | Penn Yan Regional Airport | NY | Keuka Lake |
| 7571 | Lorain County Regional Airport | OH | Black River |
| 7573 | Wayne County Airport | OH |  |
| 7575 | ProAv-Harry Clever Field (KPHD) | OH | Beaverdam Creek, Tuscarawas River |
| 7585 | Defiance Memorial Airport | OH | Maumee River |
| 7599 | St. Louis Downtown Airport | IL | Mississippi River |
| 7603 | Coles County Aviation - Flight Training | IL |  | 
| 7606 | Porter County Regional Airport | IL | Sagers Lake |
| 7622 | Ann Arbor Municipal Airport (ARB) | MI | Saline River |
| 7652 | Pocono Mountains Municipal Airport | PA | Stillwater Lake, Lake Naomi |
| 7671 | Ames Municipal Airport | IA | Ada Hayden Heritage Park Lake |
| 7704 | Tekamah Municipal Airport | NE | Missouri River |
| 7786 | Skyhaven Airport | NH | Salmon Falls River, Lily Pond |
| 7805 | Jaffrey Airport-Silver Ranch | NH | Contoocook Lake, Mtn Brook Reservoir |
| 7816 | Massena International Airport | NY | St. Lawrence River, Raquette River |
| 7838 | Alpena County Regional Airport (KAPN) | MI | Thunder Bay |
| 7861 | John F Kennedy Memorial Airport | WI | Chequamegon Bay |
| 7862 | Horlick VOR-DME (HRK) 117.7 MHz | WI | Lake Michigan |
| 7863 | Sheboygan County Memorial Int’l Airport | WI | Sheboygan River |
| 7870 | Boscobel Airport | WI | Wisconsin River |
| 7892 | Spencer Municipal Airport | IA | Little Sioux River |
| 7906 | Pine Ridge Airport - KIEN | SD | Wolf Creek |
| 7907 | Winner Regional Airport | SD |  |	 
| 7938 | Marshfield Municipal Airport | WI | Little Eau Pleine River, McMillan Marsh |
| 7962 | Johnson County Airport | WY | Lake De Smet |
| 7979 | Baker Municipal Airport - KBHK | MT | Lake Baker |
| 7987 | Jerome County Airport | ID | Clover Creek |
| 7999 | McMinnville Municipal Airport | OR | Wilamette River |
| 8000 | Hermiston Municipal Airport | OR | Cold Springs Reservoir |
| 8034 | Ford Airport | MI | Menominee River |
| 8083 | Hettinger Municipal Airport | ND |  |	 
| 8120 | Omak Airport | WA | Okanogan River, Brown Lake |
| 8133 | Paine Field | WA | Possession Sound, Puget Sound |
| 8184 | Madera Municipal Airport | CA |  | 
| 8186 | Ramona Airport | CA |  |
| 8247 | Jacksonville Executive/Craig Airport (JAXEX) | FL | Mill Cove, St. Johns River |
| 8248 | Fort Lauderdale-Hollywood Int’l Airport | FL | Atlantic Ocean |
| 9858 | Oklahoma State University | OK | Boomer Lake

Statistics for Chosen HADISDH Data Files:

| File | Latitude | Longitude | Elevation | Missing | Region | Start Date | End Date | Water |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 6501 | 33.636 | -91.756 | 85 | 266 | 4 | 20050101 | 20241130 | 1 |
| 6541 | 38.958 | -94.371 | 304.8 | 571 | 4 | 20040525 | 20241130 | 1 |
| 6640 | 28.474 | -82.454 | 19.7 | 521 | 6 | 19990101 | 20241130 | 1 |
| 6668 | 35.14 | -90.236 | 63.7 | 394 | 4 | 20040319 | 20241130 | 1 |
| 6678 | 30.393 | -86.467 | 5.4 | 482 | 6 | 19970101 | 20241130 | 1 |
| 6687 | 32.899 | -80.041 | 11.8 | 65 | 6 | 19450101 | 20241130 | 1 |
| 6697 | 36.682 | -101.505 | 948.7 | 700 | 4 | 20040319 | 20241130 | 1 |
| 6714 | 27.913 | -82.686 | 0.1 | 191 | 6 | 20060101 | 20241130 | 1 |
| 6744 | 41.351 | -71.806 | 19.8 | 675 | 5 | 20040525 | 20241130 | 1 |
| 6772 | 34.272 | -83.83 | 386.4 | 125 | 6 | 19970101 | 20241130 | 1 |
| 6783 | 33.354 | -84.569 | 241.2 | 89 | 6 | 19960101 | 20241130 | 1 |
| 6840 | 33.178 | -86.782 | 172.5 | 199 | 6 | 20020101 | 20241130 | 1 |
| 6844 | 30.029 | -91.885 | 4.8 | 361 | 4 | 20060101 | 20241130 | 1 |
| 6854 | 30.344 | -89.822 | 7.5 | 494 | 4 | 20050101 | 20241130 | 1 |
| 6870 | 32.338 | -90.221 | 101.7 | 374 | 4 | 20010101 | 20241130 | 1 |
| 6891 | 30.068 | -95.556 | 46.8 | 351 | 4 | 20060101 | 20241130 | 0 |
| 6895 | 30.361 | -95.418 | 69.4 | 172 | 4 | 19990101 | 20241130 | 0 |
| 6899 | 30.744 | -95.587 | 105.4 | 227 | 4 | 19990101 | 20241130 | 1 |
| 6901 | 32.032 | -96.399 | 135 | 406 | 4 | 19990101 | 20241130 | 1 |
| 6909 | 32.713 | -96.269 | 143 | 459 | 4 | 19990101 | 20241130 | 1 |
| 6929 | 33.183 | -96.59 | 173.4 | 72 | 4 | 20060101 | 20241130 | 1 |
| 6950 | 33.209 | -97.199 | 194.6 | 157 | 4 | 19980101 | 20241130 | 1 |
| 6963 | 30.912 | -102.917 | 917.7 | 525 | 4 | 19980101 | 20241130 | 0 |
| 6969 | 31.925 | -102.387 | 909.3 | 514 | 4 | 20010101 | 20241130 | 0 |
| 6994 | 32.259 | -107.721 | 1311.6 | 58 | 2 | 20060101 | 20241130 | 0 |
| 7032 | 33.976 | -117.625 | 193.9 | 76 | 2 | 20060101 | 20241130 | 1 |
| 7057 | 34.733 | -76.657 | 1.5 | 382 | 6 | 20010101 | 20241130 | 1 |
| 7094 | 34.984 | -81.056 | 197.4 | 130 | 6 | 20060101 | 20241130 | 1 |
| 7095 | 34.672 | -82.881 | 270.8 | 644 | 6 | 20010101 | 20241130 | 1 |
| 7100 | 34.254 | -82.153 | 188.2 | 401 | 6 | 20010101 | 20241130 | 1 |
| 7108 | 35.197 | -81.156 | 241.5 | 475 | 6 | 20010101 | 20241130 | 0 |
| 7116 | 36.048 | -79.474 | 185 | 375 | 6 | 20010101 | 20241130 | 1 |
| 7119 | 35.015 | -80.624 | 204.4 | 198 | 6 | 20010101 | 20241130 | 1 |
| 7131 | 36.77 | -90.322 | 99.6 | 336 | 4 | 20060101 | 20241130 | 1 |
| 7139 | 36.48 | -82.399 | 455.9 | 9 | 6 | 19910101 | 20241130 | 1 |
| 7152 | 35.257 | -93.095 | 115.7 | 335 | 4 | 20060101 | 20241130 | 1 |
| 7155 | 36.29 | -94.312 | 389.6 | 250 | 4 | 20020101 | 20241130 | 1 |
| 7156 | 36.371 | -92.472 | 281.1 | 394 | 4 | 19990101 | 20241130 | 1 |
| 7182 | 35.541 | -97.647 | 390.2 | 140 | 4 | 20060101 | 20241130 | 1 |
| 7193 | 34.558 | -98.417 | 326 | 280 | 4 | 20050101 | 20241130 | 1 |
| 7202 | 35.695 | -101.396 | 926.8 | 675 | 4 | 19990101 | 20241130 | 1 |
| 7239 | 36.311 | -119.623 | 76 | 212 | 2 | 19980101 | 20241130 | 0 |
| 7280 | 39.873 | -75.227 | 2.2 | 38 | 6 | 19410101 | 20241130 | 1 |
| 7286 | 38.69 | -75.362 | 15.1 | 579 | 6 | 20060101 | 20241130 | 1 |
| 7287 | 40.876 | -74.283 | 52 | 206 | 5 | 20060101 | 20241130 | 1 |
| 7311 | 39.044 | -84.672 | 262.4 | 7 | 6 | 19730101 | 20241130 | 1 |
| 7321 | 38.365 | -82.555 | 251.3 | 190 | 6 | 19730101 | 20241130 | 1 |
| 7329 | 41.563 | -83.477 | 189 | 649 | 5 | 19980101 | 20241130 | 1 |
| 7347 | 38.93 | -90.433 | 131.8 | 293 | 4 | 20010101 | 20241130 | 1 |
| 7350 | 39.585 | -85.8 | 244.4 | 346 | 6 | 20010101 | 20241130 | 1 |
| 7354 | 39.143 | -86.617 | 253.3 | 19 | 6 | 20060101 | 20241130 | 0 |
| 7357 | 39.825 | -86.296 | 247.4 | 318 | 6 | 19990101 | 20241130 | 1 |
| 7361 | 39.845 | -89.684 | 179.7 | 596 | 4 | 19730101 | 20241130 | 1 |
| 7414 | 38.072 | -102.687 | 1124 | 577 | 4 | 19950101 | 20241130 | 1 |
| 7423 | 39.228 | -106.316 | 3030.6 | 412 | 4 | 20060101 | 20241130 | 1 |
| 7424 | 40.044 | -107.888 | 1940.8 | 420 | 2 | 20060101 | 20241130 | 1 |
| 7426 | 39.23 | -106.871 | 2339.9 | 67 | 2 | 20060101 | 20241130 | 1 |
| 7432 | 39.241 | -102.282 | 1278.2 | 371 | 4 | 19990101 | 20241130 | 0 |
| 7463 | 36.212 | -115.194 | 667.4 | 114 | 2 | 19990101 | 20241130 | 0 |
| 7482 | 38.504 | -122.811 | 36.2 | 177 | 2 | 20000101 | 20241130 | 1 |
| 7489 | 40.821 | -72.867 | 20 | 501 | 5 | 20010101 | 20241130 | 1 |
| 7528 | 41.626 | -80.212 | 427.5 | 343 | 5 | 19990101 | 20241130 | 1 |
| 7531 | 40.238 | -75.555 | 88.7 | 656 | 6 | 20010101 | 20241130 | 1 |
| 7533 | 40.33 | -75.123 | 120.5 | 403 | 6 | 19990101 | 20241130 | 1 |
| 7534 | 39.919 | -76.877 | 141.4 | 126 | 6 | 20060101 | 20241130 | 1 |
| 7538 | 41.046 | -78.411 | 459.9 | 561 | 5 | 20010101 | 20241130 | 1 |
| 7549 | 43.35 | -76.383 | 143.5 | 254 | 5 | 20060101 | 20241130 | 1 |
| 7553 | 42.108 | -77.984 | 637.6 | 93 | 5 | 20060101 | 20241130 | 0 |
| 7555 | 40.65 | -75.448 | 117.4 | 671 | 5 | 19730101 | 20241130 | 1 |
| 7562 | 42.644 | -77.053 | 267.4 | 337 | 5 | 20060101 | 20241130 | 1 |
| 7571 | 41.346 | -82.179 | 241 | 162 | 5 | 19980101 | 20241130 | 1 |
| 7573 | 40.873 | -81.889 | 336.8 | 553 | 5 | 19990101 | 20241130 | 0 |
| 7574 | 39.361 | -84.521 | 184.7 | 660 | 6 | 19990101 | 20241130 | 1 |
| 7575 | 40.47 | -81.422 | 271.7 | 355 | 6 | 19990101 | 20241130 | 1 |
| 7585 | 41.336 | -84.429 | 215 | 335 | 5 | 19980101 | 20241130 | 1 |
| 7599 | 38.564 | -90.149 | 123.4 | 140 | 4 | 20060101 | 20241130 | 1 |
| 7603 | 39.474 | -88.272 | 216.4 | 98 | 6 | 20060101 | 20241130 | 0 |
| 7606 | 41.454 | -86.998 | 234 | 585 | 5 | 19990101 | 20241130 | 1 |
| 7622 | 42.224 | -83.74 | 250.6 | 308 | 5 | 20060101 | 20241130 | 1 |
| 7652 | 41.137 | -75.377 | 574.6 | 537 | 5 | 20010101 | 20241130 | 1 |
| 7671 | 41.99 | -93.619 | 281.5 | 182 | 3 | 20060101 | 20241130 | 1 |
| 7704 | 41.763 | -96.18 | 312 | 170 | 3 | 19950101 | 20241130 | 1 |
| 7786 | 43.279 | -70.924 | 100.2 | 306 | 5 | 20010101 | 20241130 | 1 |
| 7805 | 42.807 | -72.001 | 308.4 | 328 | 5 | 19970101 | 20241130 | 1 |
| 7816 | 44.933 | -74.848 | 60.9 | 101 | 5 | 19910101 | 20241130 | 1 |
| 7838 | 45.072 | -83.565 | 208.3 | 109 | 5 | 19730101 | 20241130 | 1 |
| 7861 | 46.547 | -90.918 | 250.2 | 404 | 3 | 20010101 | 20241130 | 1 |
| 7862 | 42.759 | -87.818 | 203.6 | 163 | 5 | 19990101 | 20241130 | 1 |
| 7863 | 43.775 | -87.849 | 228.9 | 138 | 5 | 19990101 | 20241130 | 1 |
| 7870 | 43.156 | -90.678 | 203.1 | 388 | 3 | 20060101 | 20241130 | 1 |
| 7892 | 43.168 | -95.21 | 407.5 | 399 | 3 | 20060101 | 20241130 | 1 |
| 7906 | 43.026 | -102.52 | 1002 | 628 | 3 | 19990101 | 20241130 | 1 |
| 7907 | 43.389 | -99.843 | 615 | 214 | 3 | 20060101 | 20241130 | 0 |
| 7938 | 44.638 | -90.188 | 381.5 | 653 | 3 | 19920101 | 20241130 | 1 |
| 7962 | 44.381 | -106.72 | 1503.8 | 168 | 1 | 20060101 | 20241130 | 1 |
| 7979 | 46.352 | -104.261 | 902.9 | 357 | 3 | 19980101 | 20241130 | 1 |
| 7987 | 42.727 | -114.455 | 1226.6 | 263 | 1 | 20060101 | 20241130 | 1 |
| 7999 | 45.196 | -123.134 | 48.2 | 191 | 1 | 19970101 | 20241130 | 1 |
| 8000 | 45.826 | -119.261 | 195.1 | 316 | 1 | 19980101 | 20241130 | 1 |
| 8034 | 45.813 | -88.113 | 343.2 | 34 | 5 | 20060101 | 20241130 | 1 |
| 8083 | 46.011 | -102.652 | 823.2 | 143 | 3 | 19990101 | 20241130 | 0 |
| 8120 | 48.461 | -119.521 | 397.4 | 243 | 1 | 20060101 | 20241130 | 1 |
| 8133 | 47.923 | -122.283 | 167.1 | 7 | 1 | 20060101 | 20241130 | 1 |
| 8184 | 36.985 | -120.111 | 76.6 | 455 | 2 | 19990101 | 20241130 | 0 |
| 8186 | 33.038 | -116.916 | 422 | 322 | 2 | 19990101 | 20241130 | 0 |
| 8247 | 30.337 | -81.513 | 11.9 | 602 | 6 | 20050101 | 20241130 | 1 |
| 8248 | 26.079 | -80.162 | 1 | 551 | 6 | 20050101 | 20241130 | 1 |
| 9858 | 36.118 | -97.091 | 271.3 | 153 | 4 | 20020312 | 20241130 | 1 |


We then use the code for putting the NC Files into a Dataframe and clean the data using the average monthly values to fill each missing/NaN value. The code to accomplish this can be found in the "Load HADISDH Data into Dataframe" file.

# National Solar Radiation Database (NSRDB):

National Renewable Energy Laboratory (NREL): National Solar Radiation Database (NSRDB)
The NSRDB is provided in annual .h5 files and currently spans 1998-2020 with data files stored in Hierarchical Data Format Version 5 (HDF5).
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

We will use the following files to extract the solar radiation output variable (GHI) from the NSRDB:

NSRDB Source File Names for .h5pyd Files:

| NSRDB Source File Names |
| :-: |
/nrel/nsrdb/v3/nsrdb_2006.h5
/nrel/nsrdb/v3/nsrdb_2007.h5
/nrel/nsrdb/v3/nsrdb_2008.h5
/nrel/nsrdb/v3/nsrdb_2009.h5
/nrel/nsrdb/v3/nsrdb_2010.h5
/nrel/nsrdb/v3/nsrdb_2011.h5
/nrel/nsrdb/v3/nsrdb_2012.h5
/nrel/nsrdb/v3/nsrdb_2013.h5
/nrel/nsrdb/v3/nsrdb_2014.h5
/nrel/nsrdb/v3/nsrdb_2015.h5
/nrel/nsrdb/v3/nsrdb_2016.h5
/nrel/nsrdb/v3/nsrdb_2017.h5
/nrel/nsrdb/v3/nsrdb_2018.h5
/nrel/nsrdb/v3/nsrdb_2019.h5
/nrel/nsrdb/v3/nsrdb_2020.h5
/nrel/nsrdb/v3/nsrdb_2021.h5
/nrel/nsrdb/v3/nsrdb_2022.h5
/nrel/nsrdb/v3/nsrdb_2023.h5
/nrel/nsrdb/v3/nsrdb_2024.h5

The code that takes the HADISDH and extracts and combines the data with the NSRDB data can be found in the "Combine_HADISDH_NSRDB_Data" file. 

# National Center for Environmental Information/National Oceanic and Atmospheric Administration (NCEI/NOAA):
Global Summary of the Day (GSOD) download:
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/

URLs used in the study for downloading CSV files:
|URL|
|---|
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2006/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2007/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2008/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2009/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2010/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2011/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2012/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2013/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2014/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2015/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2016/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2017/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2018/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2019/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2020/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2021/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2022/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2023/
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2024/

# Sunspot Index and Long-term Solar Observations (WDC-SILSO) - Solar Influences Data analysis Center (SIDC)
Solar activity, measured by the average daily sunspot number, comes from the WDC-SILSO (Royal Observatory of Belgium, Brussels, 2024) dataset. We will use the dataset located on the https://www.sidc.be/SILSO/datafiles webpage and download by clicking the “CSV” button under the “Total Sunspot Number” dropdown and “Daily total sunspot number [1/1/1818 - now]” subheading. The dataset specifies the total number of sunspots observed per day, which will quantify the solar activity for that day. The filename containing this dataset is SN_d_tot_V2.0.csv, which is a semi-colon delimited CSV file in the format with the first six fields being year, month, day, normalized year (month and day are represented by year fraction), total sunspot number, and sunspot number error. The file covers the period from January 1, 1818, until November 30, 2024 with daily total sunspot numbers to represent daily solar activity. 

# Ocean Oscillations Niño Index (ONI):
https://www.cpc.ncep.noaa.gov/products/analysis_monitoring/ensostuff/detrend.nino34.ascii.txt
