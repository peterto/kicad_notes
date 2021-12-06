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

Top menu
---
- File
  - Archive footprints - allows you to package footprints to share
  - Plot - allows you to export gerber files, so you can send to a manufacturer to produce your pcb
  - Export to allow you to export in other formats
  - Spectra session - 
  - Rescue
  - Revert to last back up - Kicad saves every 10 minutes, so you can go back to that.
    - You can use undo or git as well
    - You can change this is preferences and autosave
  - Save copy as, if you want to save various layouts or versions of your layouts without overwriting your projects
- Edit
  - Global deletions
    - delete items all in one go, can do multiple items
    - cleanup tracks and vias
    - move and swap layers
      - you can swap contents of one layer to another
    - change footprints: you can swap one footprint to another one (can choose from footprint library)
    - set footprint filed sizes: allows you to change font size of text designations
    - Edit all tracks and vias
  - View
    - Grid settings, only available here for custom user defined grids
      - You can switch between 2 user defined grid settings with shortcuts
    - Show ratsnest
    - Every else on the left toolbar
  - Setup menu (under file --> board setup)
    - Design Rules
      - This is where you take into account when you want your board manufactured
      - Global
        - Define width of tracks (across components) and vias (through layer)
          - You can define min/maxes and add options in the Track/Via options
      - Net
        - Allow you to create classes of nets that have specific design attributes, for instance, that have nets have large amount of currents to give them larger vias/track widths
    - Layers setup (under file --> board setup)
      - Sets how many copper layers you want, by default it is 2
      - There are some preconfig options to choose as well
      - Text and drawing
      - pads and mask properties
      - differential pairs
    - Place menu
      - copies stuff from the right hand side
    - Route menu and different pairs
      - Gives you the ability connect pads together (single track)
      - Differential pair
        - + and - belong to same differential pair, you can connect both pairs to another same differential pair, for instance one J1 connector - pad 10- can connect to to J2 connector - pad 10+\
          - if you have any high speed applications, you need to ensure both tracks have the same distance or approximately the same time, to do this you need to use the "tune differential pair length", try to go for the longest length, 
          - you can tune a single track with "tune track length", you can do this with any track 
        - Interactive Router Settings - used to route a track so that it doesn't violate the design rules
          - Walkaround - will route a track around other symbols
          - Shove - will try to push around a track
      - Inspect Menu
        - Nets - Shows all the nets
        - Measure - Measures two points
        - Design rules checker - Check layout against design rules
          - Courtyard layers - defines permitter of a footprint, each footprint has a courtyard
      - Tools Menu
        - Load netlist - load from schema from eeschema
          - To tell how to ID the footprints
            - reference ID - R2
            - timestamps - created when you created a footprint in eeschema, will add a timestamp in the .net file
          - what would you do if it IDs if a footprint is changed
            - normally when you make a eeschema change in footprint, you should choose change
          - extra footprints
            - delete the extra footprints not in the netlist
          - dry run - it'll show you in text what it does 
          - silent mode - no warnings 
        - Update PCB from Schematic - You can annotate and update a netlist from an updated eeschema netlist and add a footprint to pcbnew
        - Update footprints from library - to update all or certain footprints
        - Set Layer Pair - Choose how vias will behave, this will help if you are using more than 2 layers on a board
          - Through via - connects all copper layers
          - Micro via - You can connect from two layers, this is the same as a blind via, but very very small, uses a laser
          - Blind/Buried via - You can connect from two layers
          - You can set the defaults of what layer connects to another via a via
        - Prefences menu
          - configures environment variables, you can check all the environment variables online
          - manage footprint library
            - kicad - locally, faster and offline
            - github - from github, fetches from online
          - Add 3d viewer library, need this to show up in the 3d viewer, pulls from github
          - general settings
          - display options
            - you can choose higher quality graphic settings or faster rendering
            - dots or lines for grids
          - Legacy toolset
          - Modern toolset (accelerated) most used, you can switch to if you can spot a function that doesn't work in kicad 5
          - edit hotkeys
          - save and load project files
        - Help menu
          - hot keys list
          - documentation is local
          - getting started is local, latest is on the kicard.org

