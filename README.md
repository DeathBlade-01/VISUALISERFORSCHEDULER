# File Transfer PWA

A React-based visualization tool for analyzing and comparing scheduler performance across multiple trial runs. This application helps researchers and developers visualize makespan, security utility metrics, and performance trends for various scheduling algorithms.

## Who is this for?
- **Researchers** working on scheduling algorithms and optimization
- **Data Scientists** analyzing scheduler performance metrics
- **System Architects** comparing different scheduling strategies
- **Students** studying parallel computing and task scheduling
## Installation

    
### Install and Run with npm


#### 1. Download/clone the project:

    git clonehttps://github.com/DeathBlade-01/VISUALISERFORSCHEDULER
    cd VISUALISERFORSCHEDULER


#### 2. Install npm:

    npm install 

#### 3. Start the server:

    npm run dev


The application will open in your browser at **http://localhost:5173** (or the next available port).


### The CSV File Format

The application prompts user to input CSV files having the following format:

TRIAL RUN 1 - DEADLINE == 984.0624460973564 SECURITY UTILITY == 16.5132
SCHEDULER,TRIAL_RUN,MAKESPAN,UTILITY
HSMS,1,894.6022237248694,16.5132
SimpleQLearningScheduler,1,892.7340675140497,9.828999999999999
EnhancedQLearningScheduler,1,845.209387131297,9.828999999999999
HSMS+ANYSHIELD,1,983.9787218311548,33.5116
HSMS+PSOShield,1,983.8664990275564,28.48480000000001

TRIAL RUN 2 - DEADLINE == 1050.5 SECURITY UTILITY == 0.0
SCHEDULER,TRIAL_RUN,MAKESPAN,UTILITY
HSMS,2,920.5,18.2
...

#### Format Requirements

- Each trial starts with: TRIAL RUN [number] - DEADLINE == [value] SECURITY UTILITY == [value]

- Followed by a header row: SCHEDULER,TRIAL_RUN,MAKESPAN,UTILITY

- Data rows contain: scheduler name, trial number, makespan value, utility value

- Multiple trials can be included in a single file    

## How To Use

- **Upload Data**: Click the "Upload CSV" button and select your trial data file

- **Configure Settings**:

    - Use the Settings panel to select which schedulers to compare
    - Customize colors for each scheduler by clicking the color picker


- **Navigate Trials**: Use the trial selector to view different trial runs

- **Analyze Trends**: Scroll down to see performance trends across all trials

- **Export Results**:

    - Click "Export as Images" to save all visualizations as PNG files
    - Click "Export Text Report" to generate a formatted text summary
## FAQ

#### Q. What metrics does this tool visualize?

**A.** The tool visualizes two primary metrics:

    -**Makespan**: The total execution time for task completion (lower is better)
    -**Security Utility**: A measure of security performance for the scheduler (higher is better)

Rankings are determined first by utility (**higher is better**), and then by makespan (**lower is better**) as a tiebreaker.

#### Q. Can I compare schedulers across multiple trials?

**A.** Yes! The application automatically aggregates data from all trials in your CSV file. The trend charts at the bottom show how each scheduler performs across all trial runs, making it easy to identify consistent performers and outliers.


#### Q. How are my settings saved?

**A.** Your scheduler selections and custom colors are automatically saved to **browser storage**. That is, the settings are persistent as long as the session information is not cleared. 

#### Q. What file formats are supported?

**A.** The application currently supports CSV and TXT files containing trial run data in the specified format. The parser is flexible with spacing but requires the exact header format for each trial run.

#### Q. Why are some schedulers missing from my visualization?

**A.** Make sure the scheduler is selected in the Settings panel. By default, all schedulers are selected when you upload a file, but you may have deselected some for focused comparison. Click "Show Settings" and check the scheduler checkboxes.

#### Q. Can I export my visualizations for presentations?

**A.** Yes! Use the "Export as Images" button to download PNG images of all trial comparisons and trend charts. These high-quality images (2x resolution) are perfect for presentations, papers, or reports.
## Demo
TODO: ADD LATER

## Features

- **Interactive Data Upload** - Import CSV files containing trial run data
- **Multi-Trial Analysis** - Compare scheduler performance across multiple trial runs
- **Customizable Visualization** - Select specific schedulers to compare and customize their colors
- **Performance Metrics** - Visualize both makespan (execution time) and security utility
- **Trend Analysis** - Track scheduler performance trends across all trials
- **Export Capabilities** - Export visualizations as images
- **Persistent Settings** - scheduler selections and color preferences are saved automatically





## Future Vision

This project is primarily maintained for the research work that I am currently doing along with my usual academics. 

The main objective was to have a much more flexible and more intuitive tool to dynamically show the performance of differnet algorithms to analyse various trends and outliers. 

My future goals with this project is as follows: 

        1. Add another graph generator comparing execution times of the schedulers.

        2. Display the exec. times and variations across a large data set (ex: performance across multiple similar structured DAGs, and show the average, min and max values)

        3. Offer different forms of visualisations
