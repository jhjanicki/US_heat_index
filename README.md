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

## Data
NOAA maximum heat index forecast
Link: https://ftp.wpc.ncep.noaa.gov/shapefiles/heatindex/

## Some example outputs (testing different colors)
<img width="882" alt="Screenshot 2023-06-28 at 10 46 12" src="https://github.com/jhjanicki/US_heat_index/assets/6565011/3e428b2d-c2d5-4b46-afb5-47f24d06fd7a">
<img width="865" alt="Screenshot 2023-06-28 at 10 45 39" src="https://github.com/jhjanicki/US_heat_index/assets/6565011/486d3ccc-bb42-469a-9070-1b7c4f696e39">
