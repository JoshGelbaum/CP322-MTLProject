# Multi-Task Learning for EV Charging Demand Forecasting
CP322 - Machine Learning (Group 8)
# Overview
The rapid adoption of electric vehicles introduces significant variability in power grid loads. Traditional forecasting methods often treat energy consumption, session duration, and station occupancy as isolated problems. This project introduces a Multi-Task Learning (MTL) neural network to forecast these intrinsically correlated metrics simultaneously.

Using real-world data from Boulder, Colorado (2021–2022), combined with NOAA weather data, our model learns a universal representation of the "grid state." By leveraging Homoscedastic Uncertainty Weighting, the model dynamically balances regression and classification losses, achieving superior performance in energy forecasting compared to single-task baselines.

Data Engineering and Preparation

# Installation & Setup
The code is written as a Jupyter Notebook (.ipynb) and is optimized for Google Colab.

Running on Google Collab

*   Upload Project: Click File > Upload notebook and select the CP322_Project_Code.
*   Mount Drive: The code expects a Google Drive folder structure.

*   Create a folder in your Google Drive named CP322_Project_Folder.
*   Inside that, create a subfolder named data.


*   Runtime: Ensure you are using a GPU for faster training. Go to Runtime > Change runtime type > T4 GPU.


# How to Run the Program

The notebook is structured sequentially. You should run the cells in order from top to bottom.

Data Gathering & Cleaning:

*   Run the first few cells. These will automatically download the Boulder EV dataset from the web API.

*   It cleans the data (removes errors like >24hr sessions or <1min charges) and merges it with weather data.

*   Output: It generates a file final_training_data.csv and hourly_training_data.csv in your data folder.

Feature Engineering:

*   This section transforms the raw logs into a "Station-Hour" timeline.
*   It fills in the "gaps" (hours where no cars were charging) with zeros, which is crucial for the model to learn when not to predict high demand.

Model Training

*   Run the Training Loop cell. This is the longest step (approx. 45 mins for 20 epochs).
*   Watch the logs: You will see a printout for every epoch.

Evaluation:
*   The final cells run the model on the "Test Set" (data from Oct-Dec 2022) to see how well it predicts the future.

Want to thank my groupmates, Kyler, Paul, Abdul, Eric, and Ryan
