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

(Optional) You may wish to disable the native Octoprint GCode Viewer, or else the UI will try to 
show both tabs, which may become confusing.

# Release notes
- 1.0: initial version, no bells or whistles, minimal deviation from native GCode Viewer plugin