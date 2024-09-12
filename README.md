# BundleMagic
Bundle Mag!c is a LabVIEW plugin that augments right-click menu options on the block diagram for:

- Cluster and class wires and terminals
- Unbundle- and bundle-by-name nodes
- Refnum terminals and wires
- Property and Invoke nodes
- Class constants and controls

A dialog is provided to search and select cluster items, properties, methods, and LabVIEW classes, automating the placement of bundle- and unbundle-by-name nodes, property nodes, and invoke nodes when clicking on the appropriate terminals or wires.

You can add, remove, or rearrange elements from bundle- and unbundle-by-name nodes and property nodes. You can browse and change methods on invoke nodes. And you can  select and apply class types for LabVIEW class constants. 


<table class="tg">
<thead>
  <tr>
    <th class="tg-jut8" colspan="4"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000">Block Diagram </span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-sd4m"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000">Block Diagram Objects Affected</span></td>
    <td class="tg-sd4m"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000">Right-Click Menu Options</span></td>
    <td class="tg-sd4m"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000">Has Dialog?</span></td>
    <td class="tg-sd4m"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000">Notes</span></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Cluster Source Terminal</span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Class Source Terminal</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Bundle...</span></td>
    <td class="tg-1wig">*<span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Unbundle...</span></td>
    <td class="tg-1wig">*<span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Cluster Sink Terminal</span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Class Sink Terminal</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Bundle...</span></td>
    <td class="tg-1wig">*<span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Creates a constant if unwired and selected without a corresponding source terminal</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Unbundle...</span></td>
    <td class="tg-1wig">*<span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Only allowed for wired sink terminals</span></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Cluster Wires</span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Class Wires</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Bundle...</span></td>
    <td class="tg-1wig">*<span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Inserts named bundler on wire</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Unbundle...</span></td>
    <td class="tg-1wig">*<span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Inserts named unbundler on Wire</span></td>
  </tr>
  <tr>
    <td class="tg-txwv"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Unbundle By Name Element Terminals</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Move UpMove Down</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">N</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Move clicked element up or down. WIll be grayed out if move not possible</span></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="4"><br><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Bundle By Name Element Terminals</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Add Elements...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Right-Click on any cluster output terminal to add items before or after that terminal</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Remove Elements...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Remove Unwired Elements</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">N</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">If all elements are unwired, the last element will remain after this function executes</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Rearrange Elements.../ Swap Elements</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Change order of elements in un/bundler node. </span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Grayed if one element displayed</span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">“Swap” if two elements displayed</span></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Refnum Terminals</span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Refnum Wires</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Drop Properties...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Drop a Property Node with one or more properties and connect to selected terminal or wire</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Drop Method...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Drop an Invoke Node and connect to terminal or wire</span></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="5"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Property Node Element Terminals</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Move UpMove Down</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">N</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Add Properties...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Insets properties before or after the selected property. If only the default element is currently displayed, this function will replace the default element</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Remove Properties...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Select items to remove from the node</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Remove Unwired Properties</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">N</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Removes unwired terminals. Terminals with broken wires are retained.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Rearrange Properties…</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Change order and/or read/write status of displayed properties in node. Setting both R/W status of an element to false will remove the element from the node.Because multiple change types are possible, this option uses a dialog even on a two-element node</span></td>
  </tr>
  <tr>
    <td class="tg-txwv"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Invoke Node</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Browse Methods...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Browse and set method of Invoke Node</span></td>
  </tr>
  <tr>
    <td class="tg-txwv" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Class Constant</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Browse Classes...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Change class of class constant</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Copy Class Name to Clipboard</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">N</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-lea3" colspan="4"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Front Panel Functions</span></td>
  </tr>
  <tr>
    <td class="tg-txwv"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Refnum Control</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Browse Classes...</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Y</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000">Change class of refnum control</span></td>
  </tr>
</tbody>
</table>

* Bundling or unbundling clusters with one enclosed element will occur without a dialog; Single element clusters where the element is unnamed will drop an unnamed un/bundler node without a dialog


<br/><br/>

<p>
<img src="documents/Bundle Magic Images_1.png">
<img src="documents/Bundle Magic Images_2.png">
<img src="documents/Bundle Magic Images_3.png">
<img src="documents/Bundle Magic Images_4.png">
</p>

# Version History
## v 1.1 (planned)
### New Features
- Dialog search fields now accept multiple search terms
- New (Un)Bundle by name and Property Node actions:
  - Nodes with two elements will display “Swap” instead of “Rearrange…” in the contextual menu and will be swapped without a dialog
  - Cluster and property elements can be moved up and down using the “Move Up” and “Move Down” contextual menu items
- Added dialog when support files are being (re)built
### Bug Fixes
- Corrected a bug where error cluster terminals on a case structure’s selector tunnel would not present bundle/unbundle menu items
- Corrected issue on dialog open where cursor would not always appear in filter string control
- Attempted to correct a bug where removing multiple cluster or property elements (including removing unwired elements) could cause LabVIEW to crash 
- Attempted to correct issue where created Block Diagram items remain selected. (Marching ants are shown but don’t march)
- Corrected issue where Browse Classes dialog might not show scripting or private classes on load
- Corrected issue where a dot (“.”) in a cluster element label (eg “Numeric.1”) would prevent most BundleMagic cluster operations to fail
- Corrected issue where Menu items “Remove Properties…” and “Rearrange Properties…” were selectable when only one property element was displayed
- Corrected unexpected behavior when using arrow keys on a dialog tree
- Corrected issue where tabbing from a dialog's filter when tree had no selectable items didn't work. Now tab will advance to the "Done" button.
- Corrected issue where the class selection dialog allowed selection of more than one class

### Changes and Improvements
- Support files are now based on the LabVIEW display name (such as “LV2023 Q3") rather than just the year, in order to capture any property/class or method changes in major LV releases.
- Removing unwired elements no longer removes elements with broken wires
- Fixed issue where BundleMag!c dialogs could appear partially offscreen, including a situation where the dialog could not be moved
- Dialog filters 
  - If dialog filter matches a parent item, its children are no longer removed
  - When filter matches child item, its selectable parent is not grayed out
  - When neither parent nor child matches filter, both are removed (previously left parent in tree, grayed)
  - Cluster filtering was refactored to remove (rather than collapse height of) filtered items
- Arrow key dialog behaviors:
  - From the filter, the down arrow key goes to the first selectable item in the tree, and the up arrow key goes to the last selectable item in the tree
  - Arrow keys now cycle on tree items
- Tabbing in dialogs
  - You can now use the Shift-Tab keyboard shortcut to return to the dialog filter from tree
  - Tab cycling in dialogs now goes filter-tree-done-filter, unless there are no items in the tree selector, in which case the tree is skipped
- The Class dialog tree is now fully collapsed when the dialog opens, expands upon filtering, and collapses again when the filter value becomes empty

## v 1.0 (April 2020)
Initial Release

