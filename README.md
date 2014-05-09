1. What you need to install for this tutorial
   GDAL, topojson and QGIS

2. Where did I grab the original data
   http://www.naturalearthdata.com/download/10m/cultural/ne_10m_admin_0_countries_lakes.zip
   http://www.naturalearthdata.com/download/10m/cultural/ne_10m_admin_1_states_provinces_lakes.zip
   http://www.naturalearthdata.com/download/10m/cultural/ne_10m_populated_places.zip

3. Convert the data file Shapefile --> GeoJSON  -->TopoJSON

   ogr2ogr -f GeoJSON -where "gu_a3 = 'NZL' AND scalerank=6" states.json ../source/ne_10m_admin_1_states_provinces_lakes.shp
   topojson --id-property adm1_cod_1 -p name -p code=iso_3166_2 -p code_hasc -o states_nzl.topo.json states.json

4. How to run it. under your folder with index.html

    python -m SimpleHTTPServer 9999

5. reference

   Let’s Make a Map - http://bost.ocks.org/mike/map/
   Interactive Map with d3.js http://www.tnoda.com/blog/2013-12-07