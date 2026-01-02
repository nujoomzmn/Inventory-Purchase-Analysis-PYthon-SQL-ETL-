# Inventory & Purchase Analysis

## 📊 Overview
Comprehensive inventory and purchase analysis for a beverage distribution company. Combines multiple data sources to create a consolidated summary table for business intelligence and reporting.

## 🚀 Features
- **Data Integration**: Combines 6 CSV files into unified SQLite database
- **Vendor Performance Analysis**: Calculates key business metrics
- **Summary Table Creation**: Generates consolidated `vendor_sales_summary` table
- **Exploratory Data Analysis**: Statistical summaries and data quality checks
- **Database Storage**: Stores processed data for efficient querying

## 📁 Data Sources
| File | Rows | Columns | Description |
|------|------|---------|-------------|
| begin_inventory.csv | 10,000 | 9 | Initial inventory levels by store |
| end_inventory.csv | 10,000 | 9 | Ending inventory levels by store |
| purchases.csv | 10,000 | 16 | Purchase transactions with vendor details |
| purchase_prices.csv | 10,000 | 9 | Product pricing information |
| sales.csv | 10,000 | 14 | Sales transactions |
| vendor_invoice.csv | 5,543 | 10 | Vendor invoice summaries |

## 🔧 Technologies Used
- **Python** - Primary programming language
- **Pandas** - Data manipulation and analysis
- **SQLite** - Database management
- **SQLAlchemy** - Database connection and operations
- **Matplotlib/Seaborn** - Data visualization

## 📈 Key Metrics Calculated
### Basic Information
- Vendor details
- Brand descriptions
- Actual price vs purchase price

### Sales Metrics
- Total sales quantity
- Total sales dollars
- Total sales price
- Total excise tax

### Purchase Metrics
- Total purchase quantity
- Total purchase dollars
- Total freight cost

### Performance Indicators
- **Gross Profit**: SalesDollars - PurchaseDollars
- **Profit Margin**: (GrossProfit / SalesDollars) × 100
- **Stock Turnover**: SalesQuantity / PurchaseQuantity
- **Sales-to-Purchase Ratio**: SalesDollars / PurchaseDollars

## 🗂️ Database Schema

inventory.db
├── begin_inventory
├── end_inventory
├── purchases
├── purchase_prices
├── sales
├── vendor_invoice
└── vendor_sales_summary (derived table)



## 📊 Analysis Insights
### Data Characteristics
- **1,668** unique vendor-brand combinations
- **Sales quantities**: 25 to 20,460 units per vendor-brand
- **Negative gross profits** across most records
- **Low stock turnover** (mean: 0.000707)

### Performance Optimization
The `vendor_sales_summary` table enables:
- Query computation time reduction (minutes → milliseconds)
- Faster dashboard loading
- Single source of truth for vendor metrics

## 🛠️ Setup and Usage

### Prerequisites
```bash
pip install pandas sqlalchemy matplotlib seaborn

