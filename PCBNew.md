PCBNew
---

UI and layout
- Layout sheet - right corner, file page settings
- typical for new projects is 1.27 mm or 2.54 mm
- zoom to fit

Mouse shortcuts 
--
- scroll to zoom
- press middle scroll to pan
- right click for context menu for item that you are on top of 

hotkeys
--
- preferences --> hotkeys to make changes
- grid menu on the top toolbar

Left toolbar
--
- Disable any rules checking, sometimes you want to create a layout without creating a schematic first, sometimes you want to create a layout that isn't prescripted in your schematic
- hide/show grid
- polar (round) to rectangular (cartesian) coordinates, typical is cartesian (rectangular)
- units
- shape of cursor
- ratsnest - shows/hides the connections between pins of components
- fill zone - it shows continuous copper area of the board
- perimetter of the copperfield
- outline copper field 
- hides/shows pad outlines or solids
- hides/shows tracks in outlines or solids
- high contrast
- show/hide layers manager (right side)

Top toolbar
--
- Save
- Page settings
- Footprint editor - access to design custom footprints
- Footprint viewer - has access to all the footprint libraries, can view in 3d
- undo
- redo
- print
- plot - for manufacturing boards, to export necessary files for manufacturer
- redraw
- zoom out
- zoom in
- zoom to fit
- zoom to selection
- find components in text
- read netlist - allows to read netlist created in eeschema, so you can start working on the layout 
- design rules check - for pcbnew to check for errors
- layer selector, you can use hotkeys to get to each layer
- drop down - how wide tracks are
- drop down - via - electrical connections between two layers on a board, select diameter of the via between boards
- grid size
- zoom settings
  
Netlist
--
- netlist = schematic diagram

Designs rules check
--
- Start DRC, it shows what's unconnected
- too close tracks to various components
- You can control by editing design rules

Right toolbar
--
- Route tracks - to create tracks (x)
- Delete tracks (D)
- Track properties (E)
- You can connect back and front tracks with a via, add vias ()
- 1 - Standard mode, go to standard before going to another mode
- 2 - highlight net, it highlights a net/wire on the window
- 3 - display local ratsnet, shows which elements belong to a component
- 4 - Add footprint (O), you can add component that is not in your schematic, you would need to disable design rules check to be able to draw a track to another component, then re-enble when you've finished
- Graphics tools
  - Edge.cuts layer - outline of the board, you need to use the edge.cuts layer to be able to draw the permetter of the board and you can draw it with "Add graphic lines"
  - "Add graphic circle" tool to add a mounting hole to mount to a box
  - "Add graphic arc" - to draw an arc, you draw from center to radius and then draw and commit the arc
  - Add mounting holes, circle graphics tool when in edge.cuts layer
    - You can add it with a footprint, mountinghole library, you can modify it by properties
  - "Add fill zones" - copper fill, area on the pcb with copper that has been left in tact, also called copper pore, typically used as a ground, also used to reduce amount of etching chemicals, may need to tweak grid settings to something smaller
    - select net
    - clearance - how close to other elements the copper fill is
    - min width - how narrow the fill is
    - default pad connection - controls how the copper fill is connected to the pads, typically use thermal relief , small traces around the pad, doesn't fully fill copper around pad or else the pad can get too hot
    - light green is the copper fill, dark are the wires on the board in the 3d viewer
  - Add custom graphics
    - F.SilkS and B.SilkS to add lines
    - You can also add footprint libraries for graphics, in the symbols library

Status Bar
---
- left side information of the project
- when you select an element, it will show informtion on the elemnet
- right side: zoom, absolute coordinates of cursor, distance value
- Permanent measurements
- 
