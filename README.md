# event-explorer

## Summary

This code defines a Python GUI application called **Event Explorer** that helps you load, explore, and modify experimental or run-based data stored in `.npz` or `.h5` (HDF5) files. It uses the `tkinter` library for the GUI and organizes the data in a hierarchical tree structure for easy navigation. Key features include:

1. **Data Loading**  
   - Supports `.npz`, `.h5`, and `.hdf5` files.  
   - Loads the data into a Python dictionary for in-memory manipulation.  

2. **Tree View of Data**  
   - Uses a `Treeview` widget to display nested structures (dict, list, ndarray).  
   - Expands and collapses the data so you can explore it interactively.

3. **Context Menus & Operations**  
   - Right-click on different nodes for context-specific actions, such as:
     - **Pick Events** (marking event indices).
     - **Pick Arrivals** (for strain arrival picking).
     - **Extract Slopes**.
     - **Min/Max** computations on arrays.
     - **Extract Events** (cutting out time windows around event indices).
     - **Edit Strings**.
   - These actions launch specialized `tkinter` windows (imported from `views/`) for data plotting or data editing.

4. **Plotting & Editing**  
   - Double-clicking array items launches a simple plotting view.  
   - GUI prompts allow you to add or remove items (e.g., events, runs) and edit string fields.

5. **Data Saving**  
   - You can save the modified data back to an `.npz` file.

6. **Dependencies**  
   - **Python 3**  
   - `tkinter` (built into most Python installations)  
   - `numpy`  
   - `h5py`  
   - Additional modules found in `views/` (e.g., `PointsPickingView`, `SimplePlottingView`, etc.)  
   - A custom module called `tpc5` (used for reading multi-channel data).

## File Structure

- **`EventExplorer` class (in the main file)**  
  - Manages the main application window and data tree.  
  - Handles data loading (`load_npz`, `load_hdf5`), saving, and updating the tree.  
  - Responds to menu commands that trigger data editing or specialized view dialogs.

- **`views/*`**  
  - Contains various view classes for interactive plotting or data picking (e.g., `SimplePlottingView`, `PointsPickingView`, etc.).  

- **`tpc5`**  
  - A custom module providing functions to read multi-channel signals, sampling rates, etc.

## Usage

1. **Install Dependencies**
   ```bash
   pip install numpy h5py matplotlib
