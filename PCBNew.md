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


Design principles and concepts
---

Schematic symbols
--
- US standard - IEEE
  - R_US symbol library
- EU - IEC
  - R_ symbol library
- more EU symbols than US, doesn't matter what you use, but you need to use the same standard in your entire project


FR4
--
- Fiberglass with epoxy resin, it's flame retardant
  - light and strong
- Other materials that can be used are HTG, Paper based with PF resins, aluminium, and various other TG rigid and flex boards


Traces/Tracks
--
- Traces, are conductive paths made of copper, provides electricity between two pads
- traces are protected from corrosion by thge solder mask and they take the solder masks color
- If you are driving a large current through a component, you should use a larger width trace, > 20mA, 
- keep traces to 0.3mm, you can have more traces closer together and reduce size of the PCB

Pads/holes
--
- most prominent features of PCB
- TH - throughhole, a physical hole from one side of pcb to the other, easier for beginners to use
  - plated through hole (PTH) are the most common - default, a drill creates a hold and copper is filled in the hole that touches both sides of the PCB, vias are constructed in a similar fashion, but are much smaller, so you can't put a component pin in. 
  - non-plated through only cover one side and do not fill the hole
- SMD - Surface mount device, pads that exist only on single layer, smaller, so you can add more components and have a smaller pcb, can be populated by automated pick and place machines
  - Uses pads in various shapes, round and rectangular pads are the most popular, but any size can be created

Via
--
- similar to throughhole pads, but covered with solder mask instead of having the copper exposed
- Types of vias
  - buried - between 2 layers that aren't the top and bottom
  - blind - between the top or bottom and another layer 
  - through - from the top and bottom layers
  - micro - same as a blind, but very small, uses lasers instead of a drill

Annular ring
--
- Area of the pad that surrounds a via or throughhole
- normally the ring width is right in the middle of the hole

Solder mask
--
- copper can oxidize creating a pale green layer on the trace, solder mask protects the copper from oxidization
- prevents solder bridges between pads or traces
- Can be in a variety of colors

Silkscreen
--
- text and artwork, most commonly it is white, but can be black or yellow

Drill bit and drill hit
--
- drill bit - used to create holes, vias and cut outs, made of tungsten carbide from 0.3mm, 0.6mm and 1.2mm
- very small holes usually micro vias, lasers are used
- drill hit - the location on the PCB where the drill bit comes in contact with the PCB and creates a hole
  
Surface mounted devices
--
- If you want very many components, you want to use SMD and easy to manufacture in large quantities

Gold Fingers
--
- Gold plated connectors placed on the edge of a PCB
- useful for interconnecting one board to another, like a NES cartridge, can be used for thousands of times before they start to wear

Panel
--
- A manufacturer can create multiple PCBs in one panel, this is similar to a sticker page that has lots of different sized stickers all on one page 
- To remove a PCB there are defined breakaway routes that you can use to snap off

Solder paste and paste stencil
--
- Soft and sticker material (at room temp), like normal solder to attach SMD components, normally uses a syringe for application on the board, use of tweezers to pick and attach the components
- Board is placed in an oven or a heatgun is used to heat the solder paste to make it solid
- Solder paste can come in a tub, where you can use a stencil to apply it like icing on a cake, used for large scale production, stencils are normally made of stainless steel
- Part is placed in a reflow oven to bake the solder paste to harden it

Pick and place
--
- Used to assemble and place components on a SMD board
- Composed of repo of components, conveyor belt to bring in board, counters that optically recognize the board and an arm with suction to grab and place the component to the board 

Schematic Design Workflow
--
1. Setup
   1. Set grid size - from preferences menu --> Preferences --> Eeschema --> display options
      1. 25 mils is good for the grid 
   2. Page settings
      1. File menu
         1. Date, revision number and title, same as in PCBNew
2. Symbols
   1. Add symbols to sheet
      1. Graphical representations of what you are designing, Add then all to the sheet.
      2. Use the symbol chooser to place symbols on the sheet
   2. Create symbols if needed
3. Arrange, annotate, associate
   1. Arracnge symbols in functional blocks
      1. Move the symbols in place and prepare to wire them, keep wire short and have as few angles as possible
   2. Annotate symbols
      1. Annotate the symbols after they are arranged, symbols will have question marks and switch to numbers when they are annotated
   3. Associate with footprints
      1. 
4. Wire
   1. Signals
      1. Wires connect symbols to each other. Each wire is connected to a pin and creates a net
      2. Each wire from one symbol to one other symbol is called a net, nets have an automatically assigned name if not given a custom name
   2. Power (PWR_FLAG)
      1. GND and +5V are special symbols for power
5. Nets
   1. Customize net names - You do not need to name all nets, but important ones you should name, such as the power ones, GND or +5V one, typically they are used with wider traces
      1. attenenate nets
      2. data or address buses
      3. 
6. Electrical Rules Check
   1. Run ERC - Good habit to regularly use the ERC, like regularly compiling your code
   2. Fix errors
   3. Repear ERC
7. Comments
   1. Add text information, you can use text labels for comments to give more information about your design and create functional groupings of components
   2. Add graphics
8. Netlist
   1. Generate Netlist for PCBNew
      1. Need to export this for PCBNew to read in, forces you to adhere to better designing and faster and more accurate iteration

PCB Layout Workflow
--
1. Setup
   1. Setup grid
   2. Set design rules
2. Outline and Constraints
   1. Define size and shape
   2. Define mounting holes
   3. Define cutouts
3. Footprints
   1. Place components on board
   2. Arrange user interface components
   3. Arrange in functional blocks
   4. Complete placement
4. Route
   1. Critical traces
   2. Power
   3. Everything else
5. Copper fills
   1. Create GND fill
   2. Create V+ fill if necessary
6. Silkscreen
   1. Add text information
   2. Add graphics
7. Design rules check
   1. Run DRC
   2. Fix errors
   3. Repeat DRC
8. Manufacture
   1. Create Gerber files
   2. Verify Gerber files
   3. Upload Gerber files to manufacturer
9.  

Shape and Size
--
- 

Layers
--
- 
 
Traces
--
- 

