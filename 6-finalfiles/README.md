# Space Weather Data Collection Project

This project collects and processes data from NASA's DONKI API to analyze the relationship between Coronal Mass Ejections (CMEs) and Geomagnetic Storms (GSTs).

## Requirements Met

### Part 1: CME Data Collection
- [x] Correctly constructed query URL with CME endpoint, dates, and API key
- [x] GET request implementation with JSON response handling
- [x] Data preview using json.dumps with indent=4
- [x] DataFrame creation with required columns (activityID, startTime, linkedEvents)
- [x] Proper handling of missing linkedEvents
- [x] Implementation of extract_activityID_from_dict function with try-except
- [x] Correct column type conversions and renaming
- [x] Filtering for GST-related events

### Part 2: GST Data Collection
- [x] Correctly constructed query URL with GST endpoint
- [x] GET request implementation with JSON response handling
- [x] Data preview using json.dumps with indent=4
- [x] DataFrame creation with required columns
- [x] Proper handling of missing linkedEvents using explode()
- [x] Application of extract_activityID_from_dict function
- [x] Correct column type conversions and renaming
- [x] Filtering for CME-related events

### Part 3: Data Merging and Export
- [x] Correct merging of CME and GST DataFrames
- [x] Row count verification
- [x] Time difference calculation in hours
- [x] Statistical analysis using describe()
- [x] CSV export without index

## Implementation Details

1. Data Verification:
   - API connection testing
   - Data structure validation
   - Required fields checking

2. CME Data Processing:
   - Extraction of relevant fields
   - Handling of nested event data
   - Type conversions and data cleaning

3. GST Data Processing:
   - Extraction of Kp index values
   - Handling of linked events
   - Data type standardization

4. Data Analysis:
   - Calculation of time differences
   - Statistical summary generation
   - Data export for further analysis

## Setup Instructions

1. Clone the repository
2. Create a .env file with your NASA API key:
   ```
   NASA_API_KEY="your-api-key-here"
   ```
3. Install required dependencies:
   ```
   pip install pandas requests python-dotenv
   ```
4. Run the Jupyter notebook:
   ```
   jupyter notebook retrieve_data.ipynb
   ```

## Output

The script generates a CSV file in the 6-output directory containing:
- GST and CME IDs
- Start times for both events
- Time difference in hours
- Additional event details

## Data Sources

- NASA DONKI API (https://api.nasa.gov/)
  - CME endpoint: /DONKI/CME
  - GST endpoint: /DONKI/GST

## Notes

- The time difference calculations help understand the temporal relationship between CMEs and GSTs
- Data is filtered to include only linked events for accurate analysis
- Error handling is implemented throughout the process
