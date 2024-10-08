# Product-Management-System
This project is a Product Sales Management System built using Node.js, Express, and MongoDB. The system provides an API for managing product data, retrieving transaction statistics, and generating various reports, including category counts and sales data across different price ranges.
# features
Retrieve a list of products, transactions, and statistics.
Get transaction data with search, filter, and pagination options.
View product sales statistics, including total sales, sold items, and unsold items.
Generate bar charts for product sales within specific price ranges.
Retrieve product category counts for sales data.
Easily import product data from a JSON file.

# Technologies Used
Node.js - JavaScript runtime for building server-side applications.
Express.js - Fast, unopinionated, minimalist web framework for Node.js.
MongoDB - NoSQL database for storing product and transaction data.
Mongoose - MongoDB object modeling for Node.js.
dotenv - Loads environment variables from a .env file.
Cors - For handling cross-origin requests.

API Endpoints
Here is a list of the available API endpoints:

1. Get All Products
Endpoint: /api/v1/products/
Method: GET
Description: Retrieves a list of all products, sorted by date of sale in descending order.
2. Get All Transactions
Endpoint: /api/v1/products/transactions
Method: GET
Query Parameters:
search: (optional) Search products by title, description, or price.
page: (optional) Specify the page number for pagination. Default is 1.
perPage: (optional) Specify the number of items per page. Default is 10.
Description: Retrieves transactions with search and pagination functionality.
3. Get Product Sales Statistics
Endpoint: /api/v1/products/statistics
Method: GET
Query Parameters:
month: (required) The month name (e.g., January, February).
Description: Retrieves statistics on total sales, sold items, and unsold items for a specific month.
4. Get Category Counts (Pie Chart Data)
Endpoint: /api/v1/products/categorycounts
Method: GET
Query Parameters:
month: (required) The month name (e.g., January, February).
Description: Retrieves counts of products sold, grouped by category, for a specific month.
5. Get Bar Chart Data (Price Ranges)
Endpoint: /api/v1/products/bar-chart/:month
Method: GET
URL Parameters:
month: (required) The month name (e.g., January, February).
Description: Retrieves product sales data categorized by price ranges for a specific month.
Controller Logic
1. getProduct
Fetches and returns all products from the database, sorted by the most recent date of sale.
2. getAllTransactions
Supports filtering transactions by title, description, and price.
Provides pagination and a total record count for large datasets.
3. getStats
Aggregates and returns the total sales, number of sold and unsold items for a given month.
Utilizes MongoDB aggregation pipeline for efficient calculations.
4. getCategoryCounts
Groups products by category and returns counts for each category, based on sales data for a given month.
5. getBarChartData
Splits products into price ranges and counts the number of products in each range for a specific month.


Database Seed Script
The project includes a seed script for importing product data from a JSON file into MongoDB.
How to Run:
node data/import.js --import
File location: data/products.json
This will populate the Product collection in MongoDB.

Error Handling
The project uses a custom error handling middleware and an AppError class for handling operational errors. It ensures meaningful error messages and status codes are returned for each error scenario.
