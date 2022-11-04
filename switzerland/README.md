# Switzerland

Get the data as shapefile from the bottom of https://www.swisstopo.admin.ch/en/geodata/landscape/boundaries3d.html

After unpacking, convert all those shapefiles to CSV (including geometries) with 
````
for i in *.shp;
do ogr2ogr -f CSV $i.csv $i -lco GEOMETRY=AS_WKT;
done
````
, with a hat tip to https://gis.stackexchange.com/a/7448/164845

Then you have a bunch of CSV files, with a bijective BFS_NUMMER and some more information.

The BFS_NUMMER is present in the data from the old import in Switzerland, see for example the ['Kehrsatz' Relation](https://www.openstreetmap.org/relation/1682505) and in the [swisstopo data](https://map.geo.admin.ch/?time=None&lang=de&topic=swisstopo&bgLayer=ch.swisstopo.pixelkarte-farbe&layers=ch.swisstopo.swissboundaries3d-gemeinde-flaeche.fill&E=2602626.05&N=1195665.20&zoom=7) (click on the red 'Kehrsatz').