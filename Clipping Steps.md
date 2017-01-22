### Clipping a georeferenced scanned Sanborn map 

Clipping is the QGIS term for removing the borders and other unneeded areas of a map. If you did this by hand you might call it trimming.

First draft—have to run through this again and make sure all the steps are here
Can some of these steps be combined? Seems tedious to create all these pieces, but creating multiple paths in one Clipping item didn't seem to work.

1. Select the georeferenced map in QGIS
2. Select the map in layers, and right click and select zoom to layer. (You'll need to see the whole map)
3. Layer > Create Layer > New Shapefile (Cmd-Shift-N on a macOs)
4. Select the Polygon option
5. Select the existing item in the field list and click remove field (need to see if this is really necessary)
6. Fill in name (suggest using the page no and Clip, e.g. 17a Clip)
7. Accept other defaults and add to Field list
8. Click OK
9. Name the same as in Step 6 (or similar, so you can track each file)
10. Click on the new file created in the Layers menu. Right click and Toggle Editing (on)
11. Select Add Feature and now draw the outline of the mask or clipping layer. (See below for recommendations on where to click)
12. While inside the new mask, right click and save or whatever (forgot)
13. Toggle Editing off and save (do you have to rename again)
11. Raster > Extraction > Clipper
12. Select input file, i.e., the raster map, e.g., 17a 1894 Sanborn
12. Name the file (this will be the new map) using a more complete name, e.g., 17a 1894 Sanborn Clipped.tif (default is tif)
13. Select mask layer created above
14. Click on no data value 0 (makes the surround transparent)
14. Accept other options
15. Click OK and processing will begin
16. A dialog box announcing success will pop up 
17. Close the Clipper set up box (why doesn't it go away on its own)
18. Unselect the old scan and clipping layer and see if everything is OK
19. You may notice the black surroundi around the map. If so you may have missed a step 14. Delete this new layer and go back to step 11

#### Guidelines on clipping paths
Each map will be different
1. There usually is a very definite kink in near the center that needs to be followed. 
2. Usually going down the middle of the street will work. There may be rough outlines of buildings across the street, but they are usually complete on the adjoining sheet.
#### Notes
Could clip before georeferencing, but for two reasons better to do afterwards. First is that many sheets have already been georeferenced by others (and it can be good to have the border information for other reasons). Second, it's easier to deal with a georeferenced map in QGIS.
One good reason to clip before. The binding line gets morphed and is difficult to trim along.
Another is that you could do with a simple crop if it's a simple trim.

#### References
1. http://www.qgistutorials.com/en/docs/raster_mosaicing_and_clipping.html
2. https://github.com/mtop/speciesgeocoder/wiki/Tutorial-for-creating-polygons-in-QGIS drawing freehand shapes. See Drawing polygons.png  to see the icons to click on.
