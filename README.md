# SQLAlchemy and Flask Homework Solution: Analysis of the climate in Hawaii

## Background

To help with the trip planning for a long holiday vacation in Honolulu, Hawaii, I decided to do a climate analysis about the area.
In Part 1 of the analysis I used SQLAlchemy ORM queries, Pandas, and Matplotlib. 
In Part 2 of the analysis I designed a Flask API based on the queries developed in Part 1.

### Before reading the homework csv data files and coding in sql

1. I created a new repository in GitHub for this project called `sqlalchemy`. 
2. Inside the new repository I cloned the new repository to my computer.
3. Inside my local Git repository, I created a directory/folder for the assignment and named it SurfsUp.  
4. I downloaded
  
### Files including data used for the SQL database tables

* EmployeeSQL/Data/departments.csv - information about the 9 departments (id number and name of department)
* EmployeeSQL/Data/dept_emp.csv - information about the cross reference between employee number and department number (which department each of the employees worked at)
* EmployeeSQL/Data/dept_manager.csv - information about the cross reference between a manager's employee number and department number (which department each of the 24 managers worked at)
* EmployeeSQL/Data/employees.csv - information about each of the 300,024 employees (employee id, title, birth date, first name, last name, sex, and hire date)
* EmployeeSQL/Data/salaries.csv - information about each of the 300,024 employees' salary (employee id, salary)
* EmployeeSQL/Data/titles.csv - information about each of the 7 titles (title id, title)

### Entity Relationship Diagram (ERD) of the 6 tables (csv files) and SQL code files

* QuickDBD-Free Diagram_EmployeeSQL.png - image file of the ERD 
* EmployeeSQLschema.sql - sql file of the table(s) schemata that was run to create the tables for the 6 csv files in PostgreSQL v14/pgAdmin4  (exported from QuickDBD after creating ERD)
* EmployeeSQLtablecreation.sql - another version of sql code to create tables for the 6 csv files in EmployeeSQL database
* EmployeeSQLanalysis.sql - sql code to answer the data analysis questions 1-8

## Analysis Questions

1. List the employee number, last name, first name, sex, and salary of each employee.

2. List the first name, last name, and hire date for the employees who were hired in 1986.

3. List the manager of each department along with their department number, department name, employee number, last name, and first name.

4. List the department number for each employee along with that employee’s employee number, last name, first name, and department name.
