# EP_ThermResilience

The goal of the EP_ThermResilience Toolbox is to help building designers to convert building performance models for the purpose of energy analysis into models for thermal resilience analysis. Currently the toolbox script published is a proof of concept that contains 2 components - 1) a model conversion component that intakes EnergyPlus idf file of a building (for energy analysis) and converts it into a model for passive survivability analysis (to simulate power outage); and 2) a standardized dashboard to analyze the results after energy plus simulation. Details about the toolbox and an example analysis completed with the toolbox have been published in a journal article (https://www.tandfonline.com/doi/full/10.1080/19401493.2024.2365381).

Note that the functions will be improved continuously and new functions will be developed as our research on thermal resilience of buildings progresses. For updates on our research, please visit (https://hab.civmin.utoronto.ca/people/aeric-siu/)

# How to use the tool

The proof of concept tool right now is published as a jupyter notebook, in which users can make a copy and run on their desktop. To begin, make a copy of the notebook and install the required libraries.

## Required Libraries
The tool box is developed with the following libraries:

eppy==0.5.56 <br />
pandas==1.3.4 <br />
plotly==5.4.0 <br />
numpy==1.20.3 <br />
dash==2.3.1 <br />
ipython==7.29.0 <br />

## User Input

Several user inputs are needed to get started:

1) Setup file/folder paths in the "Load energy model and set output path" container, then hit run
![alt text](https://github.com/CYS-647/EP_ThermResilience/blob/main/images/Step1_PathSetup.PNG?raw=true)

2) Define the disruptive event, then hit run
![alt text](https://github.com/CYS-647/EP_ThermResilience/blob/main/images/Step2_EventDefinition.PNG?raw=true)

## Convert models

4) Run all containers from "Compile disruptive event start and end date/time" up to "Save converted file". There are multiple steps that needs to be run, each are organized into corresponding containers. Since this is a proof of concept tool, some bugs and errors may occur, please note this in the Issues section, or contact the authors of the tool, we will try our best to help with troubleshooting.

## Run EnergyPlus Simulation

5) Run EnergyPlus Simulation using the converted EnergyPlus model.

## Analysis dashboard

6) To use the analytics dashboard, please copy the csv file containing all hourly outputs into a separate folder with only the hourly results csv files. The analytics dashboard can read in multiple result files, so if there are multiple designs that need analysis, please run simulation for the design cases then put all of the hourly output csv files into the folder before running the following steps.

7) Go to the "Analysis" container, and setup the "RunPeriod_Year" and "FolderPath"(should be the folder with all the hourly output csv files), then run the container(depending on size of output files, this may take some time to complete).
![alt text](https://github.com/CYS-647/EP_ThermResilience/blob/main/images/Step7_Analysis.PNG?raw=true)
   

9) Run the "Analytics Dashboard container" then open the dashboard, there should be an url link in the container output.
![alt text](https://github.com/CYS-647/EP_ThermResilience/blob/main/images/DashboardSample_CarpetPlot.png?raw=true)
