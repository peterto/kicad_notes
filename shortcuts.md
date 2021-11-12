
UI shortcuts
---
eeschema
---

most used mouse shortcuts
--
- scroll for panning
- alt + left - zooming
- middle scroll - for panning and zooming

Most used keyboard shortcuts
--
- A - add symbol
- C - copy
- R - rotate
- G/M - drag and move
- W - draw a wire


right toolbar
---
- normal cursor
- net - it highlights full length of net or wire
- symbol chooser (A)
- place power port, can place a ground and/or power
- wire (W)
- place buses
- Place no connection, so you can place a pin that's not connected to anything
- place junction - to place two wires to be electrically connected, symbolized by a green circle
- Place net label - a way to label a wire
- Place global label
- place graphic lines or polygons - this is to create simple graphics
- Text tool - to add text labels
- bitmap image - way to add extenal images
- bottom - delete item (DEL shortcut) 

top toolbar
---
- save - save changes
- edit page settings - project information
- print - can print schema
- Plot - Like a print, but for digital files (not useful for eeschema, but used a lot of pcbnew)
- undo
- redo
- redraw - redraws sheet
- zoom in
- zoom out
- zoom to fit the whole schematic and centered
- zoom to selection that you'd like to zoom in
- schematic hierarchy - to show all schematics
- symbol editor, different from the right toolbar item, you can design a custom symbol
- symbol library browser, navigate to different libraries in kicad, once you find it, you need to use the symbol chooser to drop in your schematic sheet (like the symbol symbol on the right side)
	- use the symbol library
	- use the add symbol add on the right toolbar to add
- schematic footprint editor - to edit or add custom footprints
- schematic annotator - can automatically give names on the ? symbols, you can change the number desgination, by scrolling over a symbol and pressing e
- electrical rules check - similar to compiling code
	- note: you'll have to explicitly place a pwr_flag to assign to a wire/net or else rules check will fail for both power and gnd
- Assign footprints to symbols
	- You can combine multiple filters 
	- filters based on description
	- pin count filter
	- L - only members of selected libraries
	-D to get distance between two points
- Generate Netlist - connects schematic to layout, allows you export to various programs, may want to have two, for instance, one for throughole and one for smd components
- Edit symbol fields, you can edit properties of the components
- BOM - way to generate spreadsheet for your project, not operation out of the box, need python script, exports in csv
- Launches pcbnew
- Back import - Allows you to import from pcbnew (where you've added new components) into eeschema
- Toolbar status bar
	- middle, zoom factor
	- right, cursor coordinates
	- right, measure distances with spacebar
	- right, units
	- left side: selecting symbol will give you information on a symbol
- Menu items
	- Help - manual, tutorial
	- Preferences - configure certain parts and components, don't normally need to mod this part
		- symbol lib - can install 3rd party libs
		- general options - changing hotkeys and other visual components
		- icons
		- languages - need to change it in OS and here
		- You can import/export hotkeys
		- Save and load projects outside of defaults
	- Tools, Inspect, Place and View can be found in the top toolbar

















