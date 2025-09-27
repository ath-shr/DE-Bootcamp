# Python Fundamentals Case Study: Employee Data Management System

## Objective
Build a comprehensive employee data management system using only the Python fundamentals concepts covered in the module. This case study will test your understanding of lists, dictionaries, functions, lambda functions, comprehensions, zip/unpacking, and OOP concepts.

## Scenario
You are tasked with creating an employee management system for a growing company. The system needs to handle employee records, calculate salaries, generate reports, and manage department information using only core Python features.

## Requirements

### Data Structure
Each employee record should contain:
- `employee_id`: Unique identifier (string)
- `name`: Full name (string)
- `department`: Department name (string)
- `position`: Job title (string)
- `hire_date`: Date of hire (string in "YYYY-MM-DD" format)
- `base_salary`: Base annual salary (float)
- `performance_rating`: Rating from 1-5 (int)
- `skills`: List of skills (List[str])

### Core Features to Implement

#### 1. Employee Class
Create an `Employee` class with:
- Constructor with all employee attributes
- Methods to calculate total compensation (base + bonus)
- Method to add/remove skills
- String representation method

#### 2. Department Management
Create a `Department` class with:
- Department name and manager
- List of employees in the department
- Methods to add/remove employees
- Calculate department statistics (avg salary, headcount, etc.)

#### 3. Employee Management System
Create an `EmployeeManagementSystem` class with:
- Add/remove employees
- Search employees by various criteria
- Generate department reports
- Calculate company-wide statistics

#### 4. Data Processing Functions
Implement functions using comprehensions and functional programming:
- Filter employees by criteria (department, salary range, etc.)
- Sort employees by different attributes
- Group employees by department or other attributes
- Calculate bonuses based on performance ratings

## Sample Data
```python
sample_employees = [
    {
        "employee_id": "EMP001",
        "name": "Alice Johnson",
        "department": "Engineering",
        "position": "Senior Developer",
        "hire_date": "2022-01-15",
        "base_salary": 85000.0,
        "performance_rating": 4,
        "skills": ["Python", "SQL", "Git"]
    },
    {
        "employee_id": "EMP002", 
        "name": "Bob Smith",
        "department": "Marketing",
        "position": "Marketing Manager",
        "hire_date": "2021-06-01",
        "base_salary": 75000.0,
        "performance_rating": 5,
        "skills": ["Marketing", "Analytics", "Communication"]
    }
    # Add more sample employees...
]
```

## Specific Tasks

### Task 1: Basic Data Operations
1. Create Employee and Department classes
2. Implement methods for adding/removing employees
3. Create sample data and populate the system

### Task 2: Data Analysis with Comprehensions
1. Find all employees with salary > $70,000 using list comprehension
2. Create a dictionary mapping departments to employee counts using dict comprehension
3. Generate a list of employee names and their total compensation using zip

### Task 3: Functional Programming
1. Create lambda functions for common filtering operations
2. Use map() and filter() with lambda functions for data processing
3. Implement sorting by multiple criteria using lambda functions

### Task 4: Advanced Operations
1. Group employees by department using only core Python features
2. Calculate department averages for salary and performance
3. Find top performers in each department
4. Generate summary reports using string formatting

## Deliverables

### 1. Core Classes (`employee_system.py`)
```python
class Employee:
    # Implementation with all required methods
    
class Department:
    # Implementation with employee management
    
class EmployeeManagementSystem:
    # Main system class
```

### 2. Data Processing Functions (`data_processing.py`)
```python
def filter_employees_by_salary(employees, min_salary, max_salary):
    # Using list comprehension
    
def group_by_department(employees):
    # Using dictionaries and loops
    
def calculate_bonuses(employees):
    # Using lambda and map
```

### 3. Main Application (`main.py`)
```python
# Demonstration of all features
# Sample data creation
# Report generation
```

### 4. Test Cases (`test_system.py`)
```python
# Test all major functions
# Validate data integrity
# Test edge cases
```

## Evaluation Criteria

### Python Fundamentals Usage (40%)
- Proper use of lists, dictionaries, and tuples
- Effective list and dictionary comprehensions
- Correct implementation of functions and lambda expressions
- Proper use of zip and unpacking operations

### Object-Oriented Design (30%)
- Well-designed classes with appropriate methods
- Proper encapsulation and data protection
- Clear class relationships and interactions
- Good use of inheritance if applicable

### Code Quality (20%)
- Clean, readable code with proper naming
- Comprehensive type hints throughout
- Good error handling and validation
- Proper documentation and comments

### Functionality (10%)
- All requirements implemented correctly
- System works with provided sample data
- Handles edge cases appropriately
- Generates accurate reports and statistics

## Bonus Challenges

1. **Performance Analysis**: Compare different approaches (loops vs comprehensions) for large datasets
2. **Data Validation**: Add comprehensive input validation using only core Python
3. **Export Functionality**: Generate formatted text reports and summaries
4. **Advanced Filtering**: Implement complex multi-criteria filtering
5. **Statistical Analysis**: Calculate median, mode, and other statistics using only core Python

## Constraints

- **No External Libraries**: Use only built-in Python features
- **No File I/O**: Keep all data in memory (lists and dictionaries)
- **Type Safety**: Include type hints for all functions and methods
- **Documentation**: Every function and class must have docstrings

## Getting Started

1. **Design Phase**: Plan your class structure and relationships
2. **Implementation**: Start with basic Employee class, then build up
3. **Testing**: Test each component as you build it
4. **Integration**: Combine all components into the main system
5. **Validation**: Test with sample data and edge cases

## Sample Output

```
Employee Management System Report
================================

Total Employees: 25
Total Departments: 4

Department Summary:
- Engineering: 8 employees, avg salary: $82,500
- Marketing: 6 employees, avg salary: $71,200
- Sales: 7 employees, avg salary: $68,800
- HR: 4 employees, avg salary: $65,000

Top Performers (Rating 5):
- Alice Johnson (Engineering): $85,000
- Bob Smith (Marketing): $75,000
- Carol Davis (Sales): $72,000

High Earners (>$80,000):
- Alice Johnson: $85,000
- David Wilson: $88,000
- Eve Brown: $82,000
```

## Time Estimate
- **Beginner**: 6-8 hours
- **Intermediate**: 4-5 hours  
- **Advanced**: 2-3 hours

This case study will solidify your understanding of Python fundamentals and prepare you for more advanced data engineering concepts. Focus on writing clean, well-documented code that demonstrates mastery of core Python concepts.