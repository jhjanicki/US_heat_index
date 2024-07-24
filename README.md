# US heat index map
 Data can be downloaded in the form of shapefiles as points.  It can then be interpolated then clipped to create a raster of temperatures.

## Process
1. Load the data into QGIS as shp points
2. Click on toolbox icon in tool bar at the top 
3. Select "interpolation" then "IDW Interpolation"
    - Vector layer : choose file you’re working on in QGIS
    - Interpolation value: select Value in drop down menu
    - Click plus sign and your vector layer appears in dialogue box
    - Extent: calculate from layer -> the layer you’re working on
    - Hit Run
4. A geotiff of the heat index map is produced. Now clip it based on the US boundaries. 
5. Click on the toolbox icon again and then select "Clip raster by mask layer".
    - Input file : the interpolted layer
    - Mask layer: US shapefile (state or country level)
    - Source CRS: EPSG 4326-WGS84
    - Target CRS: EPSG 4326-WGS84
6. Now style the layer using symbology --> singleband pseudocolor 

## Data
NOAA maximum heat index forecast
Source: WPC Products in Shapefile Format (https://www.wpc.ncep.noaa.gov/html/about_gis.shtml)
Link: https://ftp.wpc.ncep.noaa.gov/shapefiles/heatindex/

Data is list by date with five files per date and ending with the day of the forecast indicated in hours so Day 3 of the Wednesday June 28 forecast is shown as with maxhi_f072_latest.tar, where 72 is hours, so the forecast for Saturday July 1.

## Some example outputs (testing different colors)
<img width="882" alt="Screenshot 2023-06-28 at 10 46 12" src="https://github.com/jhjanicki/US_heat_index/assets/6565011/93c03ffb-2503-4cc6-a2f5-0c1632cd03bf">
<img width="865" alt="Screenshot 2023-06-28 at 10 45 39" src="https://github.com/jhjanicki/US_heat_index/assets/6565011/8c90b404-a9c9-4bbc-9cfa-84e11108803d">
