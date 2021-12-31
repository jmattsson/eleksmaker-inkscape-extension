# eleksmaker-inkscape-extension

## Eleksmaker for Inkscape 1.0+ 
I got tired of keeping a legacy version of Inkscape (0.9x or lower) to create gcode for my plotter so I updated the extension. If you are getting an error with the function "bezierslopeatt" this version should (probably) work.

It now works with Inkscape 1+ and still be functional for older versions.

To install it, download the files and copy them into your extension folder (Edit>Preferences>System>Inscape Extensions).

There are a few things worth mentioning
- There is a strange bug that occurs under certain conditions when paths are grouped together that causes the GCODE output to be wrong for that path. It always appears when Hershey Text is generated. A workaround is to break the path (Shift-Cntl-G) and then re-group it if desired (Cntl-G). I think the issue is in parse_curve() but I can't find a fix. The work around of breaking and regrouping has always worked for me so I'm going to stop investigating it for now.
- It uses a lot of deprecated Inkscape API function calls for drawing the arrows showing the tool path. When these functions are removed it will break the code. For now I have hidden the deprecation warnings so they don't appear every time "Gcode output..." is run.
- The arrows that show curved toolpaths are broken in the visualisation for Inkscake 1.0 but not 1.1. I haven't bothered fixing it because the gcode output is unaffected (only the onscreen visualisation is).
- I recommend using the hatch fill function from [AxisDraw](https://wiki.evilmadscientist.com/Axidraw_Software_Installation) because it lets you chose a single or multiple closed paths to fill.

## Original Readme
This is a fork of the "EleksMaker Tool" Inkscape extension, with updates
to make it work on Inkscape 0.92.4 without weird scaling effects.

There are actually two plugins as part of EleksMaker Tool - the cutter
("Gcode output") and the hatcher ("Filling Gcode"), the former looking
like it's derived from the regular Gcode tools, and the latter appearing
to be from egg-bot. I have yet to try the hatcher, so I can offer no
comments as to whether it has scaling issues (but I didn't see the magic
values to indicate that it has issues, for what it's worth).

