# Mouse Trajectory & Circular Task Analysis — README

This project provides tools to load, process, segment, and visualize mouse trajectory data recorded during circular targeting tasks.  
It supports automatic detection of recording segments (“records” or “rounds”), coordinate centering, and multiple visualization outputs.

This project is released under **GPL v3** (see `LICENSE`).

---

## 🧩 Prerequisites

Install **Python 3.9+** and the following libraries:

- **NumPy**
- **MatPlotLib**

---

## 📁 Expected Files & Data Setup

The scripts typically use two CSV files located in the same folder:

- `001MoDe_R1.csv` — cursor data  
  *(timestamp, mouseX, mouseY, mouseInTarget)*  
- `001MoDe_R1.marker.csv` — event markers  
  *(start, pause, record)*

If you are using your own data (e.g., exported from **MouseReMoCo / RemCoco**):

- Make sure your file formatting is correct  
- Ensure column separators are clean (`,` or `;`)  
- Provide:
  - 1 file for **cursor data**
  - 1 file for **event markers**
 
---

## 🚀 Execution

When running the script (e.g., `python circular_task.py`), it will automatically:

- Load the CSV data (`np.genfromtxt`)
- Read and display header metadata
- Load and parse event markers (e.g., lines 4–26)
- Center mouse coordinates around a reference point (`centerX`, `centerY`)
- Automatically detect individual **records** using timestamp gaps or resets

---

## 📊 Outputs Generated

The scripts generate several visualizations, including:

### **Trajectory Plots**
- One **circular plot** per record
- Global plot showing the **superposition of all trajectories**
- Target visualization:  
  - Inner & outer circles  
  - Green points = inside target  
  - Red points = outside target  
- Optional screen limits (pink frame)

### **Time-Series Plots**
- X and Y coordinates over time  
- Mouse-in-target timeline  
- Combined time-aligned visualization across rounds

### **Data Processing Outputs**
- Segmented data per record  
- Recentering of coordinates  
- Computed relative time for each segment  

---
## 🧠 How the Script Works (Internal Organization)

### **Core Processing Steps**
- Load CSV(s) and detect correct delimiter and decimal format
- Extract essential columns:
  - `timestamp`
  - `mouseX`
  - `mouseY`
  - `mouseInTarget`
- Detect individual **records** (via timestamp gaps or non-zero resets)
- Recenter coordinates around the experimental target
- Build structured data for each record (relative time, centered X/Y)

### **Plotting Functions**
- Circular target plots  
- Full trajectory plots  
- X/Y over time  
- In-target signal plot  
- Combined multi-record visualizations

---

## ⚠️ Common Issues

- **RuntimeWarning (NaN)**  
  Normal if the CSV contains empty/malformed lines.

- **Empty plots**  
  Often caused by missing X/Y values — make sure the CSV contains valid numeric coordinates.

- **No detected records**  
  Timestamp format may be wrong, or separators may not match expected formatting.

- **Weird scaling / incorrect centering**  
  Header metadata or center coordinates may be missing or incorrect.

---

## 🔧 Usage Tips

- Always preprocess your CSV with **MouseReMoCo / RemCoco**  
- Ensure columns are correctly separated  
- Keep data and scripts in the same directory structure  
- Adjust filename paths inside the script when necessary
