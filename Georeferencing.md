#### Georeferencing Steps and Notes
As far as I can tell nothing connects the map you start with, or the map you create with the control points you create and (hopefully) save. 
In application QGIS
1. From menu bar, Raster > Georeferencer > Georeferencer… (Georeferencer twice duh). A new blank window will open with a icons at the top. This plugin is controlled by the icons. They are grouped by function. QGIS can't process a PDF. Convert PDFs to TIFFs first.

1. First step is to select the scanned map you're going to georeference. Click ![OpenRaster] and select your map file. 
2. Click Open (May get window asking for coordinate system—Select EPSG:3867 Pseudo Mercator WGS84) and your image should appear.
3.  Next step is to set some setting for the transformation. Click Transformation Setting ![TransSettings](Gear Wheel) Sixth icon from left
  - Transformation Type > Thin Plate Spline [Numpty](http://glaikit.org/2011/03/27/image-georeferencing-with-qgis/) explains why this is a good choice for old scanned ("vernacular)" maps. (This worked for me, but look at other tutorials if the final image quality isn't good. Note that the image quality that is output is much better than what you see in the first window; at least on macOs.)
  - Resampling Method > Cubic
  - Target SRS > EPSG-3857
  - Output raster > name the georeferenced map that will be created
    - Click on the three dots to select the folder named .... Clipped scans.
    - Make sure .tif extension is there, you may have to add it (defaults to .modified—.georef may be better)
  - Check "Load QGIS when done"
  - Click OK
  [Transformation Settings](Transformation_Settings.png)
4. Try to get some idea where you want to add points. Look at map you're working on and the current map you'll use to set coordinates.
- If it will help reading or setting the location zoom to area on both maps. You can toggle back and forth (Cmd-`) on macOS
5. Select Add Point ![Alt Text][AddPoint] by clicking icon (just to right of gear icon). It may appear selected but unless you have crosshair icon you can't click. May need to reselect Add Point [ Is there a shortcut for this???]
6. Click on the map where you want the control point to be
7. Click on From map canvas in the window that pops up. That will take you to the base map
8. Click on the corresponding location in the base map (you can zoom the map, not sure you can move around. If you need to, do; you'll just have to cancel the add point, move and then reselect add point)
9. Click OK. A red dot will appear on both maps for that control point
10. Repeat steps 5 through 10 for four or more control points. Generally near each corner and a few in the middle
11. Select Save GP Points ![SavePoints]. 5th icon from left
12. Probably use same name to avoid confusion
13. Select Georefence Point folder
14. Save
15. Click Start Georeferencing. ![StartGeoref] 2nd icon from left. Takes several seconds on my computer
16. Toggle to the base map and see that your new referenced scan is there
  - If not look for your new map in the Layers list and check that the SRS is correct
  - If still not showing check Layers order panel and make sure it's above the base map (it's usually at the bottom under your base map)

- See some of the street name changes for LA  [here](https://secure-shore-68966.herokuapp.com/streets "Croatian Restaurants site")
- Pay attention to Layers Order in QGIS if your map scan is not showing

#### References
1. [Georeferencer Plugin -QGIS](http://docs.qgis.org/2.8/en/docs/user_manual/plugins/plugins_georeferencer.html#available-transformation-algorithms). Can see icons and tutorial
2. [QGIS Tutorial](http://www.qgistutorials.com/en/docs/georeferencing_basics.html "Georeferencing Topo Sheets and Scanned Maps"). Also uses coordinates read from the scan
3. [Yet another QGIS Tutorial](https://docs.qgis.org/2.2/en/docs/training_manual/forestry/map_georeferencing.html "14.2. Lesson: Georeferencing a Map"). Part of larger tutorial. And the technique is appropriate when you're using a scanned map with coordinates which is not the case with most historical maps. But if you're doing a topo map, this is one to look at.
2. [QGIS Advanced Tutorial](http://www.qgistutorials.com/en/docs/advanced_georeferencing.html "Georeferencing Aerial Imagery")
1. [Numpty's Progress Tutorial](http://glaikit.org/2011/03/27/image-georeferencing-with-qgis/ "IMAGE GEOREFERENCING WITH QGIS"). Good reference because it uses the technique that you'll likely be using—clicking on a current map.

##### Icon references
[OpenRaster]: http://docs.qgis.org/2.8/en/_images/mActionAddRasterLayer.png "Open Raster"
[TransSettings]: http://docs.qgis.org/2.8/en/_images/mActionTransformSettings.png "Transformation Settings"
[DeletePoint]: http://docs.qgis.org/2.8/en/_images/mActionDeleteGCPPoint.png
[AddPoint]: http://docs.qgis.org/2.8/en/_images/mActionAddGCPPoint.png "Add CG Point"
[SavePoints]: http://docs.qgis.org/2.8/en/_images/mActionSaveGCPpointsAs.png "Save GCP Points As"
[StartGeoref]: http://docs.qgis.org/2.8/en/_images/mActionStartGeoref.png "Start georeferencing"

- [For other icons](http://docs.qgis.org/2.8/en/docs/user_manual/plugins/plugins_georeferencer.html#available-transformation-algorithms
)
