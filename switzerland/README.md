# Switzerland

Get the data as shapefile from the bottom of https://www.swisstopo.admin.ch/en/geodata/landscape/boundaries3d.html

After unpacking, convert all those shapefiles to CSV with 
`for i in *.shp; do ogr2ogr -f CSV $i.csv $i; done`, with a hat tip to https://gis.stackexchange.com/a/288089
Then you have a bunch of CSV files, with the BFS_NUMMER and some more information (but without geometries).

