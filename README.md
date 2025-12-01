# Circle Trajectory Analysis 

## This Python script processes mouse trajectory data (CSV), automatically detects recording sessions, and generates visualization plots.

### This Project is under GPL v3 licence (have to see LICENCE)

### Requirements

Python 3.x

Libraries: numpy, matplotlib


### Data Setup

Place your CSV data file in a data/ folder.

Ensure the file path in the script matches:

filename = "data/001MoDe_R1.csv"


### How It Works

Load Data: Reads the CSV, handling different separators (; or ,) and decimal formats.

Segmentation: Automatically detects separate records/trials based on time gaps (> 1000ms).

Visualization:

Blue Line: Trajectory path.

Green Dots: Valid points inside the target.

Red Circles: Target boundaries.

Pink Frame: Screen limits.

### Expected Results

Running the script will open a window showing:

A global superposition of all recorded trajectories.

Axes centered on the target.

Custom zoom limits (X: -300 to 400, Y: -250 to 250).
