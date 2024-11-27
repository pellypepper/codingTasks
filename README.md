# Care Management System

## Overview

The Care Management System is a Python application designed to manage a company's operations, including managing staff, regions, and client information. It allows for the addition of managers, tracking staff vacancies, and maintaining daily notes.

## Features

- **Company Management**: Create and manage company details, including name, address, phone number, and assigned managers.
- **Region Management**: Create regions associated with the company, including client details, location, team leaders, senior social workers, and staff.
- **Manager Limit**: Enforce a limit on the number of managers that can be assigned to a company.
- **Staff Vacancy Check**: Check if there are vacancies for staff within the company.
- **Daily Notes**: Maintain daily notes for each region.

## Classes

### Care

The `Care` class represents a company and includes methods for managing company details and staff.

- **Attributes**:
  - `company_name`: Name of the company.
  - `address`: Address of the company.
  - `phone`: Contact number of the company.
  - `manager`: List of managers assigned to the company.
  - `region`: List of regions associated with the company.
  - `staff`: List of staff members.

- **Methods**:
  - `__len__()`: Returns the number of managers.
  - `__str__()`: Returns a string representation of the company details.
  - `get_details()`: Returns a detailed description of the company.
  - `add_manager(manager)`: Adds a manager to the company if the limit is not reached.
  - `checkvacancy()`: Checks if there are vacancies for staff.
  - `__setItem__(time, value)`: Allows setting daily notes (note: method name should be `__setitem__`).

### Region

The `Region` class inherits from the `Care` class and represents a specific region of the company.

- **Attributes**:
  - `name`: Name of the client.
  - `location`: Location of the region.
  - `team_leader`: List of team leaders assigned to the region.
  - `senior_ss`: Senior social worker assigned to the region.
  - `staff`: List of staff members in the region.
  - `vacancy`: Indicates if there are vacancies in the region.
  - `daily_note`: Dictionary to store daily notes.

- **Methods**:
  - `__len__()`: Returns the number of staff in the region.
  - `__str__()`: Returns a string representation of the region details.
  - `get_details()`: Returns a detailed description of the client and region.
  - `__setItem__(time, value)`: Allows setting daily notes (note: method name should be `__setitem__`).

## Usage

To use the Care Management System, you can create instances of the `Care` and `Region` classes as shown below:

```python
# Create a company
company1 = Care("IBC", "07353532", "UK")
company1.manager = ["John", "Peter", "James", "Paul"]
company1.add_manager("David")

# Create a region for the company
company1_region1 = Region("IBC", "UK", "07373", "Jake", "Woolwich", "London")
company1_region1.team_leader = ["Emma"]
company1_region1.senior_ss = "Gbenga"
company1_region1.staff = ["Tom", "Jerry", "John", "Peter", "James", "Paul", "David"]
company1_region1.checkvacancy()
company1_region1.daily_note[1] = "He had lunch."

# Print company and region details
print(company1)
print(company1_region1)
