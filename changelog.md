# Version History
## v 1.1 (planned)
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
- Corrected issue where Browse Classes dialog might not show scripting or private classes on load
- Corrected issue where a dot (“.”) in a cluster element label (eg “Numeric.1”) would prevent most BundleMagic cluster operations to fail
- Corrected issue where Menu items “Remove Properties…” and “Rearrange Properties…” were selectable when only one property element was displayed
- Corrected unexpected behavior when using arrow keys on a dialog tree
- Corrected issue where tabbing from a dialog's filter when tree had no selectable items didn't work. Now tab will advance to the "Done" button.
- Corrected issue where class selection dialog allowed selection of more than one class

### Changes and Improvements
- Support files are now based on the LabVIEW display name (such as “LV2023 Q3") rather than just the year, in order to capture any property/class or method changes in major LV releases.
- Remove unwired elements no longer removes elements with broken wires
- Fixed issue where BundleMag!c dialogs could appear partially offscreen, including a situation where the dialog could not be moved
- Refactored dialog tree filters 
- If dialog filter matches a parent item, children are no longer removed
- When filter matches child item, do not gray selectable parent
- When neither parent nor child matches filter, remove both (previously left parent in tree, grayed)
- Cluster filtering was refactored to remove (rather than collapse height of) filtered items
- Arrow key dialog behaviors:
  - From the filter, the down arrow key goes to the first selectable item in the tree, and the up arrow key goes to the last selectable item in the tree
  - Arrow keys now cycle on tree items
- You can now use the Shift-Tab keyboard shortcut to return to the dialog filter from tree
- Tab cycling in dialogs now goes filter-tree-done-filter, unless there are no items in the tree selector, in which case the tree is skipped
- The Class dialog tree is now fully collapsed when the dialog opens, expands upon filtering, and collapses again when the filter value becomes empty

## v 1.0 (April 2020)
Initial Release

