# Data Pipeline in Pandas

A complete **Extract-Transform-Load (ETL)** pipeline implementation using Python and Pandas to demonstrate best practices in data engineering and data quality management.

## 📋 Project Overview

This project showcases a production-grade data processing pipeline that handles real-world data quality challenges. It processes sales transaction data through cleaning, transformation, and analysis stages.

### What is an ETL Pipeline?

- **Extract**: Retrieve raw data from source systems
- **Transform**: Clean, validate, and enrich data
- **Load**: Store processed data in target systems

## 🎯 Pipeline Stages

### 1. Extract
- Create raw sales dataset with intentional data quality issues
- Load data from CSV files
- Initial data exploration and profiling

**Sample Data Issues:**
- Missing customer names and regions
- Inconsistent date formats (`2023-01-05` vs `2023/01/06`)
- Invalid data types (quantity as string: "three")
- Invalid values (negative quantities, impossible dates)

### 2. Transform
Comprehensive data cleaning and feature engineering:

#### Data Cleaning
- **Handle Missing Values**: Fill nulls with appropriate strategies (mode, median, custom values)
- **Data Type Conversion**: Convert string quantities to numeric, dates to datetime objects
- **Remove Invalid Records**: Drop rows with unparseable dates and invalid values
- **Standardize Formats**: Title case for regions and products, strip whitespace

#### Feature Engineering
- Calculate `total_sales` = quantity × price
- Extract temporal features: year, month, day
- Create `price_category` segmentation (Budget/Mid-range/Premium)

### 3. Analyze
Generate business insights:
- Sales aggregation by region, product, and category
- Average order values and order counts
- Total revenue calculations

### 4. Load
Export processed data and reports:
- `clean_sales_data.csv` - Complete cleaned dataset with all features
- `sales_by_region.csv` - Regional performance summary
- `sales_by_product.csv` - Product performance summary
- `sales_analysis.png` - Visualization dashboard

## 📊 Dataset

**Original Records**: 10 sales transactions

**Fields**:
| Field | Type | Description |
|-------|------|-------------|
| order_id | Integer | Unique transaction identifier |
| customer_name | String | Customer name |
| region | String | Geographic region (Nairobi, Mombasa, Kisumu) |
| product | String | Product name (Laptop, Phone, Tablet, Monitor) |
| quantity | Integer | Units ordered |
| price | Float | Unit price in KES |
| order_date | Date | Transaction date |

## 🔧 Installation & Usage

### Prerequisites
```bash
python 3.8+
pandas
numpy
matplotlib
```

### Setup
```bash
# Clone the repository
git clone https://github.com/Zeddykim968/Data-Pipeline-in-Pandas.git
cd Data-Pipeline-in-Pandas

# Install dependencies
pip install pandas numpy matplotlib

# Run the notebook
jupyter notebook Data_Pipeline.ipynb
```

### Running the Pipeline
The notebook is structured for linear execution:
1. Run all cells sequentially from top to bottom
2. Each stage builds on previous outputs
3. Monitor console output for data quality metrics

## 📈 Key Metrics

After running the pipeline, you'll get:

```
Total Revenue: KES XXX,XXX
Average Order Value: KES XX,XXX
Total Orders: 8
Data Retention Rate: 80%
```

## 🎨 Visualization

The pipeline generates a 4-panel dashboard showing:
1. **Sales by Region** - Bar chart comparing regional performance
2. **Sales by Product** - Bar chart of product revenue
3. **Sales Distribution** - Pie chart of price categories
4. **Order Frequency** - Horizontal bar chart of order counts

## 💡 Key Learnings

### Data Quality Issues Addressed
- ✅ Handling missing values with appropriate imputation
- ✅ Type conversion and validation
- ✅ Detecting and removing invalid records
- ✅ Standardizing inconsistent formats

### Best Practices Implemented
- ✅ Avoid deprecated FutureWarnings (no inplace operations on copies)
- ✅ Comprehensive documentation and comments
- ✅ Modular, stage-based architecture
- ✅ Data quality tracking throughout the pipeline
- ✅ Multiple output formats for flexibility

## 🚀 Improvements Made

- **Code Quality**: Eliminated FutureWarnings by using proper pandas patterns
- **Documentation**: Added comprehensive markdown documentation
- **Error Handling**: Robust handling of type conversions with error='coerce'
- **Reporting**: Detailed metrics at each pipeline stage
- **Visualization**: Added matplotlib dashboard for insights
- **Output Flexibility**: Multiple export formats (CSV, PNG)

## 📝 Pipeline Execution Flow

```
1. Create Raw Data (10 records)
   ↓
2. Load & Explore Data
   ↓
3. Data Cleaning & Validation
   ├─ Handle missing values
   ├─ Fix data types
   ├─ Remove invalid records (2 removed)
   └─ Standardize formats
   ↓
4. Feature Engineering
   ├─ Calculate derived metrics
   ├─ Extract temporal features
   └─ Create categories
   ↓
5. Analysis & Aggregation
   ├─ Regional metrics
   ├─ Product metrics
   └─ Overall KPIs
   ↓
6. Visualization
   └─ Generate analysis dashboard
   ↓
7. Export Results (8 records)
```

## 📂 Output Files

| File | Description |
|------|-------------|
| `clean_sales_data.csv` | Cleaned dataset with all features |
| `sales_by_region.csv` | Regional aggregation report |
| `sales_by_product.csv` | Product aggregation report |
| `sales_analysis.png` | 4-panel visualization dashboard |

## 🔗 Technologies Used

- **Python 3.8+** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization
- **Jupyter Notebook** - Interactive development environment

## 📚 Use Cases

This pipeline can be adapted for:
- Order processing systems
- Financial transaction reconciliation
- Inventory management
- Customer analytics
- E-commerce data processing
- Sales reporting automation

## ⚠️ Data Quality Notes

- Original dataset: 10 records
- Removed records: 2 (invalid date and negative quantity)
- Final dataset: 8 records (80% retention rate)
- All removed records had critical data integrity issues

## 🤝 Contributing

Suggestions for improvements:
- Add error logging
- Implement unit tests
- Support multiple data sources
- Add configuration files
- Optimize for large datasets

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

**Zeddykim968** - Data Engineering & Analytics

---

**Last Updated**: 2026-04-15

For questions or suggestions, please open an issue on GitHub!