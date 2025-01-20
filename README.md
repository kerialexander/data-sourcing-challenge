# Geomagnetic Storm Prediction Dataset
Module 6 Data Sourcing Challenge

## Overview

This project aims to prepare a dataset for a prediction system to assist the NOAA Space Weather Prediction Center in predicting Geomagnetic Storms (GSTs). These storms are caused by Coronal Mass Ejections (CMEs), which are massive bursts of plasma emitted by the Sun. While Earth's magnetic shield protects us, GSTs can still impact electronic devices, such as satellites, GPS systems, and power grids. The prepared dataset combines CME and GST data sourced from the NASA API, computes the average time it takes for a CME to cause a GST, and is designed for use in Machine Learning models.

## Project Structure

The project consists of three parts:

1. **Request CME Data**

   - Fetch Coronal Mass Ejection (CME) data from the NASA API.
   - Filter and clean the data to retain relevant columns (`activityID`, `startTime`, and `linkedEvents`).
   - Expand the `linkedEvents` column and extract linked GST activity IDs.
   - Format and clean columns for further processing.

2. **Request GST Data**

   - Fetch Geomagnetic Storm (GST) data from the NASA API.
   - Filter and clean the data to retain relevant columns (`activityID`, `startTime`, and `linkedEvents`).
   - Expand the `linkedEvents` column and extract linked CME activity IDs.
   - Format and clean columns for consistency with CME data.

3. **Merge and Analyze Data**

   - Merge the CME and GST datasets based on their respective `activityID` and `linkedEvents` columns.
   - Compute the time difference between CME and GST events.
   - Export the cleaned and processed data to a CSV file for future analysis.

## Setup and Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/data-sourcing-challenge.git
   cd data-sourcing-challenge
   ```

2. **Prepare the Environment**

   - Install dependencies:
     ```bash
     pip install -r requirements.txt
     ```
   - Rename the `example.env` file to `.env` and add your NASA API key:
     ```
     NASA_API_KEY=your_api_key_here
     ```
   - Ensure `.env` is listed in the `.gitignore` file.

3. **Run the Notebook** Open and run the `retrieve_data_solution.ipynb` Jupyter Notebook to fetch and process the data.

## Dataset Details

- **Input Sources**:
  - CME Data: Includes activity ID, start time, and linked events.
  - GST Data: Includes activity ID, start time, and linked events.
- **Output**:
  - A CSV file containing merged CME and GST data with computed time differences (`timeDiff`) between events.

## Associated Files

- **new_retrieve_data_starter_code.ipynb**: Updated Jupyter Notebook to fetch, process, and clean data.
- **cme_gst.csv**: Output CSV file containing the merged and cleaned dataset.
- **example.env**: Template environment file to add your NASA API key.
- **requirements.txt**: List of dependencies required to run the project.

## Key Functions and Scripts

- **Data Fetching**:
  - Query NASA API for CME and GST data.
  - Convert JSON responses to Pandas DataFrames.
- **Data Cleaning**:
  - Expand nested data structures (e.g., `linkedEvents`).
  - Drop missing or irrelevant rows.
  - Format and rename columns for consistency.
- **Data Analysis**:
  - Merge CME and GST datasets.
  - Calculate time differences between linked events.
  - Generate descriptive statistics for the dataset.

## Usage

1. Run the notebook to fetch, process, and clean the data.
2. Inspect the generated CSV file for insights and further use in predictive modeling.

## Results and Insights

- The average time difference between CME and GST events is computed and can be used to train Machine Learning models for better prediction accuracy.
- The dataset provides structured and clean data for researchers and analysts in the field of space weather prediction.

## Resources

- [NASA API Documentation](https://api.nasa.gov/)
- [NOAA Space Weather Prediction Center](https://www.swpc.noaa.gov/)

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## Acknowledgement
I attended a tutoring session to review my initial coding and address a few issues with the merged data frame fields. 

---

Prepared by: Keri Alexander
