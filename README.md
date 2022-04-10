# Supports CNC toolpaths, which have no extrusions
This plugin is based (very) heavily on the native OctoPrint GCode Viewer, which does not show jobs that have no extrusions.

The native Octoprint GCode Viewer plugin keeps track of extruding movements and non-extruding movements.
This plugin keeps track of the lowest Z value that has occurred, and when the tool is at the lowest 
Z value, it is considered "extruding" for rendering purposes, otherwise it is "not extruding".

In the future, other options may be added, such as treating all movements as extrusions, or treating all G1 as 
extruding and all G0 as non-extruding (travel) movements.  Neither of these have been implemented yet.

![image](https://user-images.githubusercontent.com/955138/154195957-6e3de2b8-0490-4c8d-9d3b-a5434d16e528.png)

# Installing
You may install through the plugin manager by installing from this URL:

  https://github.com/vector76/cnc_gcodeviewer/archive/main.zip

For the CNC GCode Viewer to work, you must disable the default built-in GCode Viewer.  This is done here 
within the plugin manager:
![image](https://user-images.githubusercontent.com/955138/162370849-d3e2f210-017f-4a64-b703-6f353e6adc39.png)

A previous version attempted to use the "replaces ViewModel" approach to tweak the existing GCode 
Viewer so it didn't need to be disabled.  Apparently I wasn't smart enough to get that to work without 
problems, so now the built-in GCode Viewer plugin must be disabled.

# Release notes
- 1.0.3:
  - Fix problems where it wouldn't show up (due largely to stuff I still don't understand about replaces ViewModel)
  - Fix issue where single-layer model would vanish when clicking on the layer slider
- 1.0.2:
  - Tolerates gcode without spaces between words
  - Produces a layer even if there are no Z movements (movements prior to any Z movements are treated as Z=0)
- 1.0.1: Now uses replaces-viewmodel approach, so native GCode Viewer doesn't need to be disabled
- 1.0.0: Initial version, no bells or whistles, minimal deviation from native GCode Viewer plugin
