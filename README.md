# Global Retail Corp Sales Data Analysis

Global Retail Corp, a large international retail company, has been experiencing fluctuations in sales and profitability across its diverse product range and regions. To address these challenges, the company aims to optimize its product offerings, improve customer satisfaction, and enhance operational efficiency. A comprehensive analysis of the sales data is required to identify patterns, trends, and opportunities for growth.

## Dataset Overview

- **store_sales**: Contains sales order data including fields such as `sales`, `quantity`, `profit`, `order_id`, `ship_date`, `order_date`, `customer_name`, `segment`, `state`, and `market` etc.
- **sales_returns**: Contains data related to returns including `returned` status, `order_id`, and `market`.

The datasets were merged using `pd.merge` on the `order_id` field.

## Data Cleaning

1. **Checked for Duplicates**: Verified that there are no duplicate rows in the dataset.
2. **Handled Missing Values**: Replaced missing values in the `returned` column with `'No'` to indicate that the order was not returned.
3. **Renamed Columns**: Renamed columns for clarity. For example, the `order_id` column from the returns dataset was renamed to `Returned_order_id`.
4. **Standardized Names**: Standardized market names in the `returned_market` column to match those in the `market` column (e.g., changed `'US'` to `'United States'`).
5. **Changed Data Types**: Converted columns to appropriate data types, such as changing `order_date` from object to datetime.
6. **Added New Columns**: Created additional columns for analysis:
   - `delivery_time`: Calculated as the difference between `ship_date` and `order_date`.
   - `year`: Extracted from `order_date`.
   - `weektype`: Derived from `order_date`, indicating whether the day is a weekday or weekend.
