Download Mapbox Studio Classic from:
https://www.mapbox.com/mapbox-studio-classic/#win64

Got to Styles & Sources

New Style > Blank source
Add new layer (shp) >give it a description and name and hit done

Settings>export >*.mbtiles

Upload to Mapbox Also -Take note of generated mapbox id

Back to styles/sources > New Style>Choose a Basemap (dark)>Save new style

Layers>Change Source>concatenate basemap ids with upload vector layer id 
Sp: mapbox.mapbox-streets-v7,mapbox.mapbox-terrain-v2,wtgeographer.d36c7591

Add new css tab and add style for vector layer (included in css folder for repo)

Save>Settings>Download Package

Download repo from 
https://github.com/klokantech/mapbox-gl-js-offline-example.git

Download mb-utils from
https://github.com/mapbox/mbutil.git

Useful instructions for install here..
http://gis.stackexchange.com/questions/50646/is-there-any-way-to-use-mbutil-on-windows

Copy *.mbtiles from step (4) to C:\mbutil-master

cd C:\mbutil-master 

python mb-util.py *.mbtiles <new folder name here> --image_format=pbf

From index.html file from repo at >https://github.com/klokantech/mapbox-gl-js-offline-example.git
Swap out contents of function style (line 25-index.html) with json from step 10.

Under sources inside function style() comment out //url add path similiar to 
"tiles": [location.origin+location.pathname+"<pbf tiles folder name>/{z}/{x}/{y}.pbf"]:

 *** Mine seems to be working with this approach but I run into cors issues in the console instead of authorization issues.  I am hoping devs can help with this?



