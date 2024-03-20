# BundleMagic
Bundle Mag!c is a LabVIEW plugin that augments right-click menu options on the block diagram for:

- Cluster and class wires and terminals
- Unbundle- and bundle-by-name nodes
- Refnum terminals and wires
- Property and Invoke nodes
- Class constants and controls

A dialog is provided to search and select cluster items, properties, methods, and LabVIEW classes, automating the placement of bundle- and unbundle-by-name nodes, property nodes, and invoke nodes when clicking on the appropriate terminals or wires.

You can add, remove, or rearrange elements from bundle- and unbundle-by-name nodes and property nodes. You can browse and change methods on invoke nodes. And you can  select and apply class types for LabVIEW class constants. 

| Block Diagram |
| -------------------------------------------------------------- |

| Block Diagram Objects Affected                                               | Right-Click Menu Options                | Has Dialog? | Notes                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------------|-----------------------------------------|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cluster Source Terminal<br/><br/>Class Source Terminal                       | Bundle...<br/>Unbundle...               | *Y          |                                                                                                                                                                                                                                                              |
| Cluster Sink Terminal<br/><br/>Class Sink Terminal                           | Bundle...                               | *Y          | Creates a constant if unwired and selected without a corresponding source terminal                                                                                                                                                                           |
|                                                                              | Unbundle...                             | *Y          | Only allowed for wired sink terminals                                                                                                                                                                                                                        |
| Cluster Wires<br/><br/>Class Wires                                           | Bundle...                               | *Y          | Inserts named bundler on wire                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                              |
|                                                                              | Unbundle...                             | *Y          | Inserts named unbundler on Wire                                                                                                                                                                                                                              |
| Unbundle By Name Element Terminals<br/><br/>Bundle By Name Element Terminals | Move Up<br/>Move Down                   | N           | Move clicked element up or down. WIll be grayed out if move not possible                                                                                                                                                                                     |
|                                                                              | Add Elements...                         | Y           | Right-Click on any cluster output terminal to add items before or after that terminal                                                                                                                                                                        |
|                                                                              | Remove Elements...                      | Y           |                                                                                                                                                                                                                                                              |
|                                                                              | Remove Unwired Elements                 | N           | If all elements are unwired, the last element will remain after this function executes                                                                                                                                                                       |
|                                                                              | Rearrange Elements...<br/>Swap Elements | Y<br/>N     | Change order of elements in un/bunder node. Grayed if one element displayed, “Swap” if two elements displayed                                                                                                                                                |
| Refnum Terminals<br/>Refnum Wires                                            | Drop Properties...                      | Y           | Drop a Property Node with one or more properties and connect to selected terminal or wire                                                                                                                                                                    |
|                                                                              | Drop Method...                          | Y           | Drop an Invoke Node and connect to terminal or wire                                                                                                                                                                                                          |
| Property Node Element Terminals                                              | Move Up<br/>Move Down                   | N           |                                                                                                                                                                                                                                                              |
|                                                                              | Add Properties...                       | Y           | Insets properties before or after the selected property. If only the default element is currently displayed, this function will replace the default element                                                                                                  |
|                                                                              | Remove Properties...                    | Y           | Select items to remove from the node                                                                                                                                                                                                                         |
|                                                                              | Remove Unwired Properties               | N           | Removes unwired terminals. Terminals with broken wires are retained.                                                                                                                                                                                         |
|                                                                              | Rearrange Properties…                   | Y           | Change order and/or read/write status of displayed properties in node. Setting both R/W status of an element to false will remove the element from the node.Because multiple change types are possible, this option uses a dialog even on a two-element node |
| Invoke Node                                                                  | Browse Methods...                       | Y           | Browse and set method of Invoke Node                                                                                                                                                                                                                         |
| Class Constant                                                               | Browse Classes...                       | Y           | Change class of class constant                                                                                                                                                                                                                               |
|                                                                              | Copy Class Name to Clipboard            | N           |                                                                                                                                                                                                                                                              |


| Front Panel Functions |
|-----------------------|

| Front Panel Objects Affected | Right-Click Menu Options | Has Dialog? | Notes                          |
|------------------------------|--------------------------|-------------|--------------------------------|
| Refnum Control               | Browse Classes...        | Y           | Change class of refnum control |

* Bundling or unbundling clusters with one enclosed element will occur without a dialog; Single element clusters where the element is unnamed will drop an unnamed un/bundler node without a dialog


<br/><br/>

<p>
<img src="documents/Bundle Magic Images_1.png">
<img src="documents/Bundle Magic Images_2.png">
<img src="documents/Bundle Magic Images_3.png">
<img src="documents/Bundle Magic Images_4.png">
</p>

# Version History
## v 1.1 (April 2024)
### New Features
- Dialog search accepts multiple search terms
- New (Un)Bundle by name and Property Node actions:
  - Nodes with two elements will display “Swap” instead of “Rearrange…” in the contextual menu and will be swapped without a dialog
  - Cluster and property elements can be moved up and down using the “Move Up” and “Move Down” contextual menu items
- Added short flash dialog when support files are being (re)built
### Bug Fixes
- Corrected a bug where (error) cluster terminals on a case structure’s selector tunnel would not present bundle/unbundle menu items
- Corrected issue on dialog open where cursor would not always appear in filter string control
- Attempted to correct a bug where removing multiple cluster or property elements (including Removing unwired elements) could cause LabVIEW to crash 
- Attempted to correct issue where created Block Diagram items remain selected. (Marching ants are shown but don’t march)
- Corrected issue where Browse Classes dialog might not show scripting or private classed on load
- Corrected issue where a dot (“.”) in a cluster element label (eg “Numeric.1”) would prevent most BundleMagic cluster operations to fail
- Corrected issue where Menu items “Remove Properties…” and “Rearrange Properties…” were selectable when only one property element was displayed
- Remove parent items in dialog trees where no children are selected by filtering
- Corrected unexpected behavior when using arrow keys on a dialog tree
### Changes and Improvements
- Support files are now based on the LabVIEW display name (such as “LV2023 Q3") rather than just the year, in order to capture any property/class or method changes in major LV releases.
- Remove unwired elements no longer removes elements with broken wires
- Fixed issue where BundleMag!c dialogs, could appear partially offscreen, including a situation where the dialog could not be moved
- Refactored dialog tree filters 
- If filter matches parent item, do not remove its children
- When filter matches child item, do not gray selectable parent
- When neither parent nor child matches filter, remove both (previously left parent in tree, grayed)
- Cluster filtering was refactored to remove (rather than collapse height of) filtered items
- Arrow key dialog behaviors:
  - From the filter, the down arrow key goes to the first selectable item in the tree, and the up arrow key goes to the last selectable item in the tree.
  - Arrow keys now cycle on tree items
- You can now use the Shift-Tab keyboard shortcut to return to the dialog filter from tree
- Tab cycling in dialogs now goes filter-tree-done-filter…

## v 1.0 (April 2020)
Initial Release

