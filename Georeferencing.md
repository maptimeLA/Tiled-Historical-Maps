#### Georeferencing Steps and Notes
As far as I can tell nothing connects the map you start with, or the map you create with the control points you create and (hopefully) save. 
1.  
2.  EPSG 3857 option, then OK?
3.  Transformation Setting (Gear Wheel)
  - Transformation Type > Thin Plate Spline
  - Target SRS > EPSG-3857
  - Output raster > name the georeferenced map that will be created
    - Click on the three dots to select the folder named .... Clipped scans.
    - Make sure .tif extension is there, you may have to add it
  - Resampling Method > Cubic
  - Check "Load QGIS when done"
  - Click OK
4. Try to get some idea where you want to add points. Look at map you're working on and the current map you'll use to set coordinates.
- If it will help reading or setting the location zoom to area on both maps. You can toggle back and forth (Cmd-`) on macOS
5. Select Add Point by clicking icon (just to right of gear icon). It may appear selected but unless you have crosshair icon you can't click. May need to reselect Add Point [ Is there a shortcut for this???]
6. Click on the map where you want the control point to be
7. Click on From map canvas in the window that pops up. That will take you to the base map
8. Click on the corresponding location in the base map (you can zoom the map, not sure you can move around. If you need to, do; you'll just have to cancel the add point, move and then reselect add point)
9. Click OK. A red dot will appear on both maps for that control point
10. Repeat steps 5 through 10 for four or more control points. Generally near each corner and a few in the middle
11. Select Save GP Points As icon
12. Probably use same name to avoid confusion
13. Select Georefence Point folder
14. Save
15. Click Start Georeferencing. Green triangle (second icon). Takes several seconds on my computer
16. Toggle to the base map and see that your new referenced scan is there
  - If not look for your new map in the Layers list and check that the SRS is correct
  - If still not showing check Layers order panel and make sure it's above the base map (it's usually at the bottom under your base map)


- The georeferencing points created in QGIS don't seem to automatically saved. Useful to keep these for adjustments.
- See street name changes at [Greg's site](https://secure-shore-68966.herokuapp.com/streets)
- Pay attention to Layers Order in QGIS if your map scan is not showing

#### References
1. [Georeferencer Plugin -QGIS](http://docs.qgis.org/2.8/en/docs/user_manual/plugins/plugins_georeferencer.html#available-transformation-algorithms). Can see icons and tutorial
1. [QGIS Tutorial](http://www.qgistutorials.com/en/docs/georeferencing_basics.html "Georeferencing Topo Sheets and Scanned Maps")
2. [QGIS Advanced Tutorial](http://www.qgistutorials.com/en/docs/advanced_georeferencing.html "Georeferencing Aerial Imagery")
1. [Numpty's Progress Tutorial](http://glaikit.org/2011/03/27/image-georeferencing-with-qgis/)
