OBJECTIVE:
Create a simple employee hierarchy management system using OOP, functions, dictionaries, and lists.

TOPICS COVERED:
- Classes and Objects
- Functions
- Dictionaries and Lists
- Basic inheritance (bonus)

SCENARIO:
You need to build a system to manage employees in a company with different roles and departments.

SAMPLE DATA:
employee_data = [
    {"id": "E001", "name": "Alice Johnson", "department": "Engineering", "salary": 75000},
    {"id": "E002", "name": "Bob Smith", "department": "Marketing", "salary": 65000},
    {"id": "E003", "name": "Charlie Brown", "department": "Engineering", "salary": 80000}
]

department_data = [
    {"name": "Engineering", "budget": 500000, "employees": ["E001", "E003"]},
    {"name": "Marketing", "budget": 300000, "employees": ["E002"]},
    {"name": "HR", "budget": 200000, "employees": []}
]

PROBLEM 1: Employee Class
Create an Employee class with the following requirements:
- Store employee information in a dictionary attribute
- Create functions to manage salary and performance
- Use lists to track work history and projects

class Employee:
    
    def __init__(self, emp_id, name, department, salary):
        # Store employee info in dictionary
        # Initialize projects list and work history
        pass
    
    def give_raise(self, amount):
        # Update salary and add to work history
        pass
    
    def assign_project(self, project_name):
        # Add project to projects list
        pass
    
    def get_info(self):
        # Return employee information dictionary
        pass

PROBLEM 2: Department Class  
Create a Department class that manages employees:
- Use dictionary to store department details
- Use list to track employees in department
- Create functions for department operations

class Department:
    
    def __init__(self, name, budget):
        # Store department info in dictionary
        # Initialize employee list
        pass
    
    def add_employee(self, emp_id):
        # Add employee to department list
        pass
    
    def remove_employee(self, emp_id):
        # Remove employee from department list
        pass
    
    def get_employee_count(self):
        # Return number of employees in department
        pass

PROBLEM 3: Company Class
Create a Company class that manages departments and employees:
- Use dictionaries to store employees and departments
- Create functions for company-wide operations
- Combine Employee and Department classes

class Company:
    
    def __init__(self, name):
        # Initialize company with name and empty dictionaries
        pass
    
    def add_employee(self, employee):
        # Add employee to company dictionary
        pass
    
    def add_department(self, department):
        # Add department to company dictionary
        pass
    
    def transfer_employee(self, emp_id, new_dept):
        # Move employee between departments
        pass
    
    def get_total_salary_cost(self):
        # Calculate total salary expenses
        pass
    
    def get_department_summary(self):
        # Return summary of all departments
        pass
