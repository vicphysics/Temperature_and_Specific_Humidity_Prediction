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



# HADISDH (Humidity data):

The Met Office humidity data (HADISDH) datasets are stored in NetCDF or Network Common Data Form (.NC) geospatial file format. 
To access and visualize this data in Python, the required libraries are discussed with applicable python code at:

https://medium.com/analytics-vidhya/how-to-read-and-visualize-netcdf-nc-geospatial-files-using-python-6c2ac8907c7c


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
7671	41.99	    -93.619	    hadisd.3.4.1.202411p_19310101-20241201_725472-94989_humidity.nc
7704	41.763	    -96.18	    hadisd.3.4.1.202411p_19310101-20241201_725527-94978_humidity.nc
7861	46.547	    -90.918	    hadisd.3.4.1.202411p_19310101-20241201_726419-94929_humidity.nc
7870	43.156	    -90.678	    hadisd.3.4.1.202411p_19310101-20241201_726438-94994_humidity.nc
7892	43.168	    -95.21	    hadisd.3.4.1.202411p_19310101-20241201_726500-14972_humidity.nc
7906	43.026	    -102.52	    hadisd.3.4.1.202411p_19310101-20241201_726517-94039_humidity.nc
7907	43.389	    -99.843	    hadisd.3.4.1.202411p_19310101-20241201_726518-94990_humidity.nc
7938	44.638	    -90.188	    hadisd.3.4.1.202411p_19310101-20241201_726574-94985_humidity.nc
7979	46.352	    -104.261	hadisd.3.4.1.202411p_19310101-20241201_726777-94055_humidity.nc
8083	46.011	    -102.652	hadisd.3.4.1.202411p_19310101-20241201_727584-94038_humidity.nc

Region 4:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
6501	33.636	    -91.756	    hadisd.3.4.1.202411p_19310101-20241201_720175-53919_humidity.nc
6541	38.958	    -94.371	    hadisd.3.4.1.202411p_19310101-20241201_720306-53879_humidity.nc
6668	35.14	    -90.236	    hadisd.3.4.1.202411p_19310101-20241201_722054-53959_humidity.nc
6697	36.682	    -101.505	hadisd.3.4.1.202411p_19310101-20241201_722095-03030_humidity.nc
6844	30.029	    -91.885	    hadisd.3.4.1.202411p_19310101-20241201_722314-53915_humidity.nc
6854	30.344	    -89.822	    hadisd.3.4.1.202411p_19310101-20241201_722330-53865_humidity.nc
6870	32.338	    -90.221	    hadisd.3.4.1.202411p_19310101-20241201_722354-13927_humidity.nc
6891	30.068	    -95.556	    hadisd.3.4.1.202411p_19310101-20241201_722429-53910_humidity.nc
6895	30.361	    -95.418	    hadisd.3.4.1.202411p_19310101-20241201_722444-53902_humidity.nc
6899	30.744	    -95.587	    hadisd.3.4.1.202411p_19310101-20241201_722447-53903_humidity.nc
6901	32.032	    -96.399	    hadisd.3.4.1.202411p_19310101-20241201_722469-53912_humidity.nc
6909	32.713	    -96.269	    hadisd.3.4.1.202411p_19310101-20241201_722489-53911_humidity.nc
6929	33.183	    -96.59	    hadisd.3.4.1.202411p_19310101-20241201_722541-53914_humidity.nc
6950	33.209	    -97.199    	hadisd.3.4.1.202411p_19310101-20241201_722589-03991_humidity.nc
6963	30.912	    -102.917	hadisd.3.4.1.202411p_19310101-20241201_722618-23091_humidity.nc
6969	31.925	    -102.387	hadisd.3.4.1.202411p_19310101-20241201_722648-03031_humidity.nc
7131	36.77	    -90.322	    hadisd.3.4.1.202411p_19310101-20241201_723300-03975_humidity.nc
7152	35.257	    -93.095	    hadisd.3.4.1.202411p_19310101-20241201_723429-53920_humidity.nc
7155	36.29	    -94.312	    hadisd.3.4.1.202411p_19310101-20241201_723436-53922_humidity.nc
7156	36.371    	-92.472	    hadisd.3.4.1.202411p_19310101-20241201_723439-53918_humidity.nc
7182	35.541	    -97.647	    hadisd.3.4.1.202411p_19310101-20241201_723544-03954_humidity.nc
7193	34.558	    -98.417	    hadisd.3.4.1.202411p_19310101-20241201_723575-03950_humidity.nc
7202	35.695	    -101.396	hadisd.3.4.1.202411p_19310101-20241201_723635-03024_humidity.nc
7347	38.93	    -90.433	    hadisd.3.4.1.202411p_19310101-20241201_724347-53904_humidity.nc
7361	39.845	    -89.684	    hadisd.3.4.1.202411p_19310101-20241201_724390-93822_humidity.nc
7414	38.072	    -102.687	hadisd.3.4.1.202411p_19310101-20241201_724636-03013_humidity.nc
7423	39.228	    -106.316	hadisd.3.4.1.202411p_19310101-20241201_724673-93009_humidity.nc
7432	39.241	    -102.282	hadisd.3.4.1.202411p_19310101-20241201_724689-03026_humidity.nc
7599	38.564	    -90.149	    hadisd.3.4.1.202411p_19310101-20241201_725314-03960_humidity.nc
9858	36.118	    -97.091	    hadisd.3.4.1.202411p_19310101-20241201_999999-53926_humidity.nc

Region 5:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
6744	41.351	    -71.806	    hadisd.3.4.1.202411p_19310101-20241201_722151-14794_humidity.nc
7287	40.876	    -74.283	    hadisd.3.4.1.202411p_19310101-20241201_724094-54743_humidity.nc
7329	41.563	    -83.477	    hadisd.3.4.1.202411p_19310101-20241201_724287-04848_humidity.nc
7489	40.821	    -72.867	    hadisd.3.4.1.202411p_19310101-20241201_725016-54790_humidity.nc
7528	41.626	    -80.212	    hadisd.3.4.1.202411p_19310101-20241201_725104-04843_humidity.nc
7538	41.046	    -78.411	    hadisd.3.4.1.202411p_19310101-20241201_725119-54792_humidity.nc
7549	43.35	    -76.383	    hadisd.3.4.1.202411p_19310101-20241201_725146-54773_humidity.nc
7553	42.108	    -77.984	    hadisd.3.4.1.202411p_19310101-20241201_725157-54757_humidity.nc
7555	40.65	    -75.448	    hadisd.3.4.1.202411p_19310101-20241201_725170-14737_humidity.nc
7562	42.644	    -77.053	    hadisd.3.4.1.202411p_19310101-20241201_725194-54778_humidity.nc
7571	41.346	    -82.179	    hadisd.3.4.1.202411p_19310101-20241201_725214-04849_humidity.nc
7573	40.873	    -81.889	    hadisd.3.4.1.202411p_19310101-20241201_725216-04842_humidity.nc
7585	41.336	    -84.429	    hadisd.3.4.1.202411p_19310101-20241201_725254-04851_humidity.nc
7606	41.454	    -86.998	    hadisd.3.4.1.202411p_19310101-20241201_725327-04846_humidity.nc
7622	42.224	    -83.74	    hadisd.3.4.1.202411p_19310101-20241201_725374-94889_humidity.nc
7652	41.137	    -75.377	    hadisd.3.4.1.202411p_19310101-20241201_725434-54789_humidity.nc
7786	43.279	    -70.924	    hadisd.3.4.1.202411p_19310101-20241201_726056-54791_humidity.nc
7805	42.807	    -72.001	    hadisd.3.4.1.202411p_19310101-20241201_726163-54770_humidity.nc
7816	44.933	    -74.848	    hadisd.3.4.1.202411p_19310101-20241201_726223-94725_humidity.nc
7838	45.072	    -83.565	    hadisd.3.4.1.202411p_19310101-20241201_726390-94849_humidity.nc
7862	42.759	    -87.818	    hadisd.3.4.1.202411p_19310101-20241201_726424-94818_humidity.nc
7863	43.775	    -87.849	    hadisd.3.4.1.202411p_19310101-20241201_726425-04841_humidity.nc
8034	45.813	    -88.113	    hadisd.3.4.1.202411p_19310101-20241201_727437-94893_humidity.nc

Region 6:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
6640	28.474	    -82.454	    hadisd.3.4.1.202411p_19310101-20241201_722014-12818_humidity.nc
6678	30.393	    -86.467	    hadisd.3.4.1.202411p_19310101-20241201_722069-53853_humidity.nc
6687	32.899	    -80.041	    hadisd.3.4.1.202411p_19310101-20241201_722080-13880_humidity.nc
6714	27.913	    -82.686	    hadisd.3.4.1.202411p_19310101-20241201_722116-12873_humidity.nc
6772	34.272	    -83.83	    hadisd.3.4.1.202411p_19310101-20241201_722185-53838_humidity.nc
6783	33.354	    -84.569	    hadisd.3.4.1.202411p_19310101-20241201_722197-53819_humidity.nc
6840	33.178	    -86.782	    hadisd.3.4.1.202411p_19310101-20241201_722300-53864_humidity.nc
7057	34.733	    -76.657	    hadisd.3.4.1.202411p_19310101-20241201_723037-93765_humidity.nc
7094	34.984	    -81.056	    hadisd.3.4.1.202411p_19310101-20241201_723117-53871_humidity.nc
7095	34.672	    -82.881	    hadisd.3.4.1.202411p_19310101-20241201_723118-53850_humidity.nc
7100	34.254	    -82.153	    hadisd.3.4.1.202411p_19310101-20241201_723124-53874_humidity.nc
7108	35.197	    -81.156	    hadisd.3.4.1.202411p_19310101-20241201_723147-53870_humidity.nc
7116	36.048	    -79.474	    hadisd.3.4.1.202411p_19310101-20241201_723174-93783_humidity.nc
7119	35.015	    -80.624	    hadisd.3.4.1.202411p_19310101-20241201_723194-53872_humidity.nc
7139	36.48	    -82.399	    hadisd.3.4.1.202411p_19310101-20241201_723350-13877_humidity.nc
7280	39.873	    -75.227	    hadisd.3.4.1.202411p_19310101-20241201_724080-13739_humidity.nc
7286	38.69	    -75.362	    hadisd.3.4.1.202411p_19310101-20241201_724093-13764_humidity.nc
7311	39.044	    -84.672	    hadisd.3.4.1.202411p_19310101-20241201_724210-93814_humidity.nc
7321	38.365	    -82.555	    hadisd.3.4.1.202411p_19310101-20241201_724250-03860_humidity.nc
7350	39.585	    -85.8	    hadisd.3.4.1.202411p_19310101-20241201_724356-53866_humidity.nc
7354	39.143	    -86.617	    hadisd.3.4.1.202411p_19310101-20241201_724375-03893_humidity.nc
7357	39.825	    -86.296	    hadisd.3.4.1.202411p_19310101-20241201_724384-53842_humidity.nc
7531	40.238	    -75.555	    hadisd.3.4.1.202411p_19310101-20241201_725109-54782_humidity.nc
7533	40.33	    -75.123	    hadisd.3.4.1.202411p_19310101-20241201_725113-54786_humidity.nc
7534	39.919	    -76.877	    hadisd.3.4.1.202411p_19310101-20241201_725114-93778_humidity.nc
7574	39.361	    -84.521	    hadisd.3.4.1.202411p_19310101-20241201_725217-53855_humidity.nc
7575	40.47	    -81.422	    hadisd.3.4.1.202411p_19310101-20241201_725224-04852_humidity.nc
7603	39.474	    -88.272	    hadisd.3.4.1.202411p_19310101-20241201_725317-53802_humidity.nc
8247	30.337	    -81.513	    hadisd.3.4.1.202411p_19310101-20241201_747820-53860_humidity.nc
8248	26.079	    -80.162	    hadisd.3.4.1.202411p_19310101-20241201_747830-12849_humidity.nc

Region 7:

| File | Latitude | Longitude | Filename |
| :-: | :-: | :-: | --- |
| 5768 | 61.169	| -150.028 | hadisd.3.4.1.202411p_19310101-20241201_702730-26451_humidity.nc |
| 5778 | 60.129 | -149.418 | hadisd.3.4.1.202411p_19310101-20241201_702770-26438_humidity.nc |


# NCEI/NOAA (National Center for Environmental Information/National Oceanic and Atmospheric Administration):
Global Summary of the Day (GSOD) download:
https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/

# Ocean Oscillations Niño Index (ONI):
cpc.ncep.noaa.gov/products/analysis_monitoring/ensostuff/detrend.nino34.ascii.txt

# Sunspot Index and Long-term Solar Observations (WDC-SILSO) - Solar Influences Data analysis Center (SIDC)
Solar activity, measured by the average daily sunspot number, comes from the WDC-SILSO (Royal Observatory of Belgium, Brussels, 2024) dataset. We will use the dataset located on the https://www.sidc.be/SILSO/datafiles webpage and download by clicking the “CSV” button under the “Total Sunspot Number” dropdown and “Daily total sunspot number [1/1/1818 - now]” subheading. The dataset specifies the total number of sunspots observed per day, which will quantify the solar activity for that day. The filename containing this dataset is SN_d_tot_V2.0.csv, which is a semi-colon delimited CSV file in the format with the first six fields being year, month, day, normalized year (month and day are represented by year fraction), total sunspot number, and sunspot number error. The file covers the period from January 1, 1818, until November 30, 2024 with daily total sunspot numbers to represent daily solar activity. 
