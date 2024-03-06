# BundleMagic
A LabVIEW plugin for Un/Bundle, Method, and Property Node manipulation


The VIPM installation will include a dependency called LabVIEW Bug Fix for Right-Click Menu Plug-Ins by NI - Toolkit for LabVIEW Download when installing BundleMag!c in a LabVIEW version prior to LV2020.

## Feature TODOs
On Class browser, show current class of control
Arrow keys
On property, arrows should jump to next selectable line
Optimize Bundle order
	Find opposite end of wires and order bundler by vertical wire position
### Builder
	Save to LV2015 for backward compatible
### Bugs
•	helper files are not complete if dialog is closed before all elements are found.
### When building support files
- Add fast splash screen when building helper files
- On first run of function that requires support files, if files don’t exist and scripting is off, present dialog letting user know that this feature is not available unless the support files can be built, which requires scripting to be on, at least for a few minutes (doubecheck that this is true)
  - Turn scripting off, and attempt to use
  - Show FP of support builder when called
### Browse Classes on FP
When the control is shown in the Class Control on the front panel, right-clicking on the control does not activate the Browse Classes… shortcut menu (but right-clicking the Class Control border does)		.

## BundleMag!c v 1.1
### New Features
- Dialog search accepts multiple search terms
- New (Un)Bundle by name and Property Node actions:
  - Nodes with two elements will display “Swap” instead of “Rearrange…” in the contextual menu and will be swapped without a dialog
  - Cluster and property elements can be moved up and down using the “Move Up” and “Move Down” contextual menu items
- Added short flash dialog when support files are being (re)built
### Bug Fixes
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
- You can now use the Shift-Tab keybaord shortcut to return to the dialog filter from tree
- Tab cycling in dialogs now goes filter-tree-done-filter…

