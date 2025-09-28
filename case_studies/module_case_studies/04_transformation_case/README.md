# Data Transformation Case Study: E-commerce ETL Pipeline

## Objective
Build a comprehensive ETL (Extract, Transform, Load) pipeline using pandas and data transformation concepts covered in the module. This case study focuses on data loading, transformation, JSON flattening, aggregation functions, unit testing, error handling, and performance optimization.

## Scenario
You work for a growing e-commerce platform that receives data from multiple sources including web analytics, customer systems, product catalogs, order management, and third-party integrations. The data comes in various formats and requires extensive transformation before it can be used for analytics and reporting.

Your task is to create a robust ETL pipeline that can:
- Load data from multiple sources and formats
- Transform and clean data for consistency
- Handle complex nested JSON structures
- Perform aggregations for business metrics
- Ensure data quality through validation and testing
- Optimize performance for large datasets

## Requirements

### Data Sources and Formats

#### 1. Web Analytics Data (JSON)
```json
{
  "session_id": "sess_12345",
  "user_id": "user_67890",
  "timestamp": "2024-03-15T14:30:00Z",
  "page_views": [
    {
      "page_url": "/products/laptop-123",
      "page_title": "Gaming Laptop Pro",
      "time_on_page": 45,
      "scroll_depth": 0.8,
      "interactions": {
        "clicks": 3,
        "form_submissions": 0,
        "video_plays": 1
      }
    }
  ],
  "device_info": {
    "device_type": "desktop",
    "browser": "Chrome",
    "os": "Windows",
    "screen_resolution": "1920x1080"
  },
  "location": {
    "country": "USA",
    "state": "California",
    "city": "San Francisco",
    "coordinates": {
      "lat": 37.7749,
      "lng": -122.4194
    }
  }
}
```

#### 2. Customer Data (CSV)
```csv
customer_id,first_name,last_name,email,phone,registration_date,customer_tier,total_orders,lifetime_value
CUST001,John,Doe,john.doe@email.com,+1-555-0123,2023-01-15,Gold,15,2450.75
CUST002,Jane,Smith,jane.smith@email.com,+1-555-0124,2023-02-20,Silver,8,1200.50
```

#### 3. Product Catalog (JSON)
```json
{
  "products": [
    {
      "product_id": "PROD001",
      "name": "Gaming Laptop Pro",
      "category": {
        "primary": "Electronics",
        "secondary": "Computers",
        "tertiary": "Laptops"
      },
      "pricing": {
        "cost": 800.00,
        "retail": 1299.99,
        "currency": "USD",
        "discounts": [
          {"type": "seasonal", "percentage": 10, "valid_until": "2024-03-31"},
          {"type": "bulk", "min_quantity": 5, "percentage": 15}
        ]
      },
      "specifications": {
        "brand": "TechBrand",
        "model": "Pro-X1",
        "weight": "2.5kg",
        "dimensions": {"length": 35, "width": 25, "height": 2.5},
        "features": ["RGB Keyboard", "16GB RAM", "1TB SSD", "RTX 4060"]
      },
      "inventory": {
        "stock_level": 45,
        "warehouse_locations": ["WH001", "WH003"],
        "reorder_point": 10,
        "supplier_id": "SUP001"
      }
    }
  ]
}
```

#### 4. Order Data (Parquet)
- order_id, customer_id, order_date, status, total_amount, shipping_address, payment_method

#### 5. Order Items (CSV)
```csv
order_item_id,order_id,product_id,quantity,unit_price,discount_amount,total_price
OI001,ORD001,PROD001,1,1299.99,129.99,1170.00
OI002,ORD001,PROD002,2,49.99,0.00,99.98
```

### Core Features to Implement

#### 1. Data Loading Framework
- Multi-format data loading (CSV, JSON, Parquet)
- Configurable data source connections
- Incremental loading capabilities
- Error handling and retry mechanisms
- Data validation during loading

#### 2. Data Transformation Engine
- Pandas-based transformation operations
- JSON flattening for nested structures
- Data type conversions and standardization
- Data cleaning and normalization
- Custom transformation functions

#### 3. Aggregation and Analytics
- Business metric calculations
- Time-based aggregations
- Customer segmentation analysis
- Product performance metrics
- Revenue and profitability analysis

#### 4. Data Quality and Testing
- Unit tests for transformation functions
- Data validation rules and checks
- Business rule validation
- Data profiling and quality metrics
- Automated testing framework

#### 5. Performance Optimization
- Memory-efficient processing
- Parallel processing capabilities
- Chunked data processing
- Query optimization techniques
- Performance monitoring and profiling

## Specific Implementation Tasks

### Task 1: Data Loading Infrastructure
**Objective**: Build robust data loading capabilities

**Requirements**:
1. Create pandas-based data loaders for each format
2. Implement configurable data source management
3. Add incremental loading with state management
4. Handle large files with chunked processing
5. Implement comprehensive error handling

**Deliverables**:
- `data_loaders.py` with format-specific loaders
- `source_config.py` with data source configuration
- `incremental_loader.py` with state management
- `error_handler.py` with error recovery mechanisms

### Task 2: JSON Flattening and Transformation
**Objective**: Handle complex nested JSON structures

**Requirements**:
1. Implement recursive JSON flattening
2. Handle arrays and nested objects
3. Preserve data relationships during flattening
4. Create configurable flattening rules
5. Support for custom transformation logic

**Deliverables**:
- `json_flattener.py` with flattening algorithms
- `transformation_rules.py` with configurable rules
- `data_normalizer.py` with standardization functions
- Comprehensive test cases for edge cases

### Task 3: Business Metrics and Aggregations
**Objective**: Implement analytical transformations

**Requirements**:
1. Customer lifetime value calculations
2. Product performance metrics
3. Revenue and profitability analysis
4. Time-series aggregations
5. Cohort analysis and segmentation

**Deliverables**:
- `business_metrics.py` with metric calculations
- `aggregation_functions.py` with reusable aggregations
- `analytics_engine.py` with analytical workflows
- Performance benchmarks for large datasets

### Task 4: Data Quality and Validation
**Objective**: Ensure data integrity and quality

**Requirements**:
1. Comprehensive unit testing framework
2. Data validation rules and constraints
3. Business rule validation
4. Data profiling and quality scoring
5. Automated quality reporting

**Deliverables**:
- `test_transformations.py` with unit tests
- `validation_engine.py` with validation rules
- `quality_profiler.py` with data profiling
- `quality_reports.py` with automated reporting

### Task 5: Performance Optimization
**Objective**: Optimize for large-scale data processing

**Requirements**:
1. Memory-efficient pandas operations
2. Parallel processing implementation
3. Performance monitoring and profiling
4. Query optimization techniques
5. Scalability testing and benchmarking

**Deliverables**:
- `performance_optimizer.py` with optimization techniques
- `parallel_processor.py` with parallel execution
- `profiler.py` with performance monitoring
- Scalability test results and recommendations

## Project Structure

```
04_transformation_case/
├── README.md
├── requirements.txt
├── config/
│   ├── data_sources.yaml
│   ├── transformation_rules.yaml
│   ├── validation_rules.yaml
│   └── performance_config.yaml
├── data/
│   ├── raw/
│   │   ├── web_analytics/
│   │   ├── customers/
│   │   ├── products/
│   │   ├── orders/
│   │   └── order_items/
│   ├── processed/
│   │   ├── staging/
│   │   ├── transformed/
│   │   └── aggregated/
│   └── reference/
│       ├── lookup_tables/
│       └── business_rules/
├── src/
│   ├── __init__.py
│   ├── loaders/
│   │   ├── __init__.py
│   │   ├── base_loader.py
│   │   ├── csv_loader.py
│   │   ├── json_loader.py
│   │   ├── parquet_loader.py
│   │   └── incremental_loader.py
│   ├── transformers/
│   │   ├── __init__.py
│   │   ├── json_flattener.py
│   │   ├── data_cleaner.py
│   │   ├── data_normalizer.py
│   │   ├── business_metrics.py
│   │   └── aggregation_functions.py
│   ├── validation/
│   │   ├── __init__.py
│   │   ├── validation_engine.py
│   │   ├── quality_profiler.py
│   │   ├── business_rules.py
│   │   └── quality_reports.py
│   ├── optimization/
│   │   ├── __init__.py
│   │   ├── performance_optimizer.py
│   │   ├── parallel_processor.py
│   │   └── memory_manager.py
│   ├── pipeline/
│   │   ├── __init__.py
│   │   ├── etl_orchestrator.py
│   │   ├── pipeline_runner.py
│   │   └── state_manager.py
│   └── utils/
│       ├── __init__.py
│       ├── logging_config.py
│       ├── profiler.py
│       └── error_handler.py
├── tests/
│   ├── __init__.py
│   ├── test_loaders.py
│   ├── test_transformers.py
│   ├── test_validation.py
│   ├── test_optimization.py
│   ├── test_pipeline.py
│   └── test_integration.py
├── scripts/
│   ├── generate_sample_data.py
│   ├── run_etl_pipeline.py
│   ├── validate_data_quality.py
│   ├── performance_benchmark.py
│   └── generate_reports.py
├── notebooks/
│   ├── data_exploration.ipynb
│   ├── transformation_analysis.ipynb
│   ├── performance_analysis.ipynb
│   └── quality_analysis.ipynb
└── docs/
    ├── architecture.md
    ├── transformation_guide.md
    ├── performance_tuning.md
    └── api_documentation.md
```

## Sample Transformation Scenarios

### 1. JSON Flattening Example
```python
# Input: Nested web analytics JSON
nested_data = {
    "session_id": "sess_12345",
    "device_info": {
        "device_type": "desktop",
        "browser": "Chrome"
    },
    "location": {
        "country": "USA",
        "coordinates": {"lat": 37.7749, "lng": -122.4194}
    }
}

# Output: Flattened structure
flattened_data = {
    "session_id": "sess_12345",
    "device_info_device_type": "desktop",
    "device_info_browser": "Chrome",
    "location_country": "USA",
    "location_coordinates_lat": 37.7749,
    "location_coordinates_lng": -122.4194
}
```

### 2. Business Metrics Calculation
```python
def calculate_customer_ltv(customer_orders_df: pd.DataFrame) -> pd.DataFrame:
    """Calculate Customer Lifetime Value metrics."""
    
    customer_metrics = customer_orders_df.groupby('customer_id').agg({
        'total_amount': ['sum', 'mean', 'count'],
        'order_date': ['min', 'max']
    }).round(2)
    
    # Flatten column names
    customer_metrics.columns = ['total_revenue', 'avg_order_value', 'order_count', 'first_order', 'last_order']
    
    # Calculate additional metrics
    customer_metrics['days_active'] = (
        pd.to_datetime(customer_metrics['last_order']) - 
        pd.to_datetime(customer_metrics['first_order'])
    ).dt.days
    
    customer_metrics['ltv_score'] = (
        customer_metrics['total_revenue'] * 
        customer_metrics['order_count'] / 
        (customer_metrics['days_active'] + 1)
    )
    
    return customer_metrics
```

### 3. Data Quality Validation
```python
def validate_order_data(orders_df: pd.DataFrame) -> Dict[str, Any]:
    """Comprehensive order data validation."""
    
    validation_results = {
        'total_records': len(orders_df),
        'validation_errors': [],
        'quality_score': 0.0
    }
    
    # Check for required fields
    required_fields = ['order_id', 'customer_id', 'order_date', 'total_amount']
    missing_fields = [field for field in required_fields if field not in orders_df.columns]
    
    if missing_fields:
        validation_results['validation_errors'].append(f"Missing required fields: {missing_fields}")
    
    # Check for null values
    null_counts = orders_df[required_fields].isnull().sum()
    if null_counts.any():
        validation_results['validation_errors'].append(f"Null values found: {null_counts.to_dict()}")
    
    # Business rule validation
    negative_amounts = orders_df[orders_df['total_amount'] < 0]
    if not negative_amounts.empty:
        validation_results['validation_errors'].append(f"Found {len(negative_amounts)} orders with negative amounts")
    
    # Calculate quality score
    error_count = len(validation_results['validation_errors'])
    validation_results['quality_score'] = max(0, 100 - (error_count * 10))
    
    return validation_results
```

## Technical Specifications

### Performance Requirements
- Process 1M+ records within 10 minutes
- Memory usage optimization for large datasets
- Support for parallel processing
- Efficient pandas operations
- Scalable to multi-GB datasets

### Data Quality Standards
- 95%+ data completeness for critical fields
- 100% business rule compliance
- Comprehensive validation coverage
- Automated quality scoring
- Real-time quality monitoring

### Testing Requirements
- 90%+ unit test coverage
- Integration tests for end-to-end workflows
- Performance regression testing
- Data quality validation tests
- Error handling and recovery tests

### Error Handling Standards
- Graceful handling of malformed data
- Comprehensive error logging and reporting
- Automatic retry mechanisms for transient failures
- Data quarantine for problematic records
- Recovery procedures for failed processes

## Evaluation Criteria

### Technical Implementation (35%)
- Effective use of pandas for data transformation
- Proper JSON flattening and data normalization
- Efficient aggregation and analytical functions
- Performance optimization techniques
- Memory management and scalability

### Data Quality and Testing (25%)
- Comprehensive unit testing framework
- Data validation and quality assurance
- Business rule implementation
- Error handling and recovery mechanisms
- Automated quality reporting

### Code Quality and Organization (25%)
- Clean, well-documented code with type hints
- Proper project structure and modularity
- Following pandas and Python best practices
- Comprehensive logging and monitoring
- Configuration management

### Innovation and Problem Solving (15%)
- Creative solutions to complex transformation challenges
- Performance optimization innovations
- Advanced analytical implementations
- Scalability considerations
- User-friendly interfaces and documentation

## Bonus Features (Optional)

1. **Real-time Processing**: Stream processing capabilities for real-time transformations
2. **Machine Learning Integration**: Feature engineering for ML pipelines
3. **Advanced Analytics**: Statistical analysis and data mining functions
4. **Visualization Integration**: Data preparation for visualization tools
5. **Cloud Integration**: Cloud-native processing capabilities
6. **API Development**: REST API for transformation services
7. **Workflow Orchestration**: Integration with workflow management tools

## Getting Started

1. **Environment Setup**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install pandas numpy pyarrow pytest
   ```

2. **Generate Sample Data**
   ```bash
   python scripts/generate_sample_data.py --size large
   ```

3. **Run ETL Pipeline**
   ```bash
   python scripts/run_etl_pipeline.py --config config/data_sources.yaml
   ```

4. **Validate Results**
   ```bash
   python scripts/validate_data_quality.py --output-dir data/processed/
   ```

## Timeline and Milestones

### Day 1: Data Loading and Infrastructure
- Implement multi-format data loaders
- Create configuration management system
- Build error handling framework
- Set up testing infrastructure

### Day 2: JSON Flattening and Transformation
- Implement recursive JSON flattening
- Create data normalization functions
- Build transformation rule engine
- Add comprehensive test coverage

### Day 3: Business Metrics and Aggregations
- Implement analytical functions
- Create business metric calculations
- Build aggregation framework
- Add performance optimizations

### Day 4: Data Quality and Validation
- Implement validation framework
- Create quality profiling system
- Build automated testing suite
- Add quality reporting capabilities

### Day 5: Performance Optimization and Integration
- Optimize for large-scale processing
- Implement parallel processing
- Complete integration testing
- Finalize documentation and presentation

## Success Metrics

- **Functionality**: All transformation requirements implemented correctly
- **Performance**: Processing targets met for large datasets
- **Quality**: 90%+ test coverage with comprehensive validation
- **Usability**: Clear documentation and easy-to-use interfaces
- **Scalability**: System handles growth in data volume and complexity

This case study will demonstrate your mastery of data transformation concepts and prepare you for real-world ETL and data processing challenges. Focus on building a production-ready system that showcases professional data engineering skills with pandas and Python.