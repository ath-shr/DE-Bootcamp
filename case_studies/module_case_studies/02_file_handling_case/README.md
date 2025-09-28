OBJECTIVE:
Learn the difference between Full Load and Incremental Load data processing using CSV and JSON files with pandas.

TOPICS COVERED:
- Full Load vs Incremental Load concepts
- Reading CSV and JSON files with pandas
- Data merging and deduplication
- Basic data transformations and aggregations

SCENARIO:
You work for a retail company that receives daily sales data. You need to understand two ways of processing data:
- Full Load: Process all data from scratch every time
- Incremental Load: Process only new data since last run

SAMPLE DATA STRUCTURE:
Both CSV and JSON files will have the same schema. CSV file is Full load and JSON file is incremental load. Below is the structure of both file:
- transaction_id: Unique identifier
- customer_id: Customer identifier  
- product_name: Name of product sold
- quantity: Number of items
- price: Price per item
- sale_date: Date of sale

TASK 1: Create Sample Data Files
- Create the sample data with existing notebook. (_generate_sales_data.ipynb)
- sales_full.csv (complete dataset)
- sales_new.json (new transactions only)
- Both files have same schema for easy merging

TASK 2: Load Data with Pandas
Learn to load both CSV and JSON files:
- Use pd.read_csv() for CSV files
- Use pd.read_json() for JSON files
- Display basic information about datasets

TASK 3: Merge Data from Both Sources
Combine CSV and JSON data:
- Concatenate dataframes
- Handle different file formats with same schema
- Create unified dataset

TASK 4: Remove Duplicates and Apply Transformations
Clean and transform the merged data:
- Remove duplicate transactions
- Calculate total amount (quantity × price)
- Group by customer and calculate totals
- Create simple summary statistics