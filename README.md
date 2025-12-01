*Notebook Guide: Mouse Trajectory Analysis - Understanding the Excel files*

This notebook is designed to analyze and correlate the raw experimental data (001MoDe_R1.csv) with its corresponding summary markers (001MoDe_R1.marker.csv). It provides a step-by-step breakdown of the calculations required to transform raw movement data into meaningful performance metrics.

 **Requirements**

To run this notebook, ensure the following Python libraries are installed:

NumPy: For numerical operations.

Matplotlib: For plotting trajectories and visualizations.

**Data Files**

The script relies on two specific datasets located in the data/ directory:

001MoDe_R1.csv (Raw Data)

Contains high-frequency sampling of mouse positions (X, Y), timestamps, and target status (inside/outside).

Serves as the primary source for recalculating metrics.

001MoDe_R1.marker.csv (Summary Data)

Contains event markers (start/stop of trials) and pre-calculated statistics.

Serves as the "ground truth" to validate our own calculations.

**Objectives**

The main goals of this notebook are:

Data Understanding: Explore the structure and content of both CSV files.

Reverse Engineering: Demonstrate the mathematical formulas and logic used to derive the summary statistics (e.g., error rate, effective width) from the raw trajectory points.

Validation: Compare the recalculated values against the provided summary file to ensure accuracy.

**Features**

Automated Segmentation: Detects individual recording trials from the continuous raw data stream.

Metric Calculation: Explicit formulas for calculating performance metrics.

Verification: Tables comparing calculated results vs. expected results from the marker file.

**Usage**

Clone this repository.
