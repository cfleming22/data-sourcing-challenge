# NASA Space Weather Data Analysis

This project analyzes the relationship between Coronal Mass Ejections (CMEs) and Geomagnetic Storms (GSTs) using NASA's DONKI API. The analysis helps understand how CMEs affect Earth's magnetic field and the timing between these solar events and their geomagnetic effects.

## Background

Coronal Mass Ejections (CMEs) are massive bursts of solar plasma that can interact with Earth's magnetic shield, potentially causing Geomagnetic Storms (GSTs). These storms can affect satellites, GPS systems, and power grids. This analysis helps understand:
- The relationship between CMEs and GSTs
- The typical time delay between a CME and its resulting GST
- Patterns in solar weather that could improve prediction systems

## Data Sources

The data is sourced from NASA's DONKI (Database Of Notifications, Knowledge, Information) API:
- CME data: https://api.nasa.gov/DONKI/CME
- GST data: https://api.nasa.gov/DONKI/GST

## Setup

1. Clone this repository:
```bash
git clone [repository-url]
cd data-sourcing-challenge
```

2. Create a Python environment (optional but recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install pandas requests python-dotenv
```

4. Create a .env file with your NASA API key:
```
NASA_API_KEY="your-api-key-here"
```
You can get an API key from: https://api.nasa.gov/

## Files

- `retrieve_data.ipynb`: Jupyter notebook containing the data collection and analysis
- `.env`: Configuration file for API key (not tracked in git)
- `6-output/collected_data.csv`: Output file containing merged CME and GST data

## Analysis Process

1. CME Data Collection:
   - Fetch CME data from NASA API
   - Process and clean the data
   - Extract linked GST events

2. GST Data Collection:
   - Fetch GST data from NASA API
   - Process and clean the data
   - Extract linked CME events

3. Data Merging and Analysis:
   - Merge CME and GST data
   - Calculate time differences
   - Generate statistics

## Results

The analysis provides insights into:
- The number of CMEs that result in GSTs
- The typical delay between a CME and its associated GST
- Statistical distribution of CME-GST time differences

## Requirements

- Python 3.x
- pandas
- requests
- python-dotenv
- Jupyter Notebook

## License

This project is licensed under the terms of the MIT license.
