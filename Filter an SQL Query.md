##  Project Description
My role in this project is to investigate potential security issues within the organization by analyzing data from two tables "log_in_attempts" and "employees.” using SQL queries, I should retrieve specific data to assess security concerns, such as after-hours login attempts, login attempts on specific dates, unauthorized login attempts from outside Mexico, and details of employees based on their department and location.
Retrieve after hours failed login attempts
To investigate potential security incidents that occurred after business hours, I will query the "log_in_attempts" table using SQL filters. Specifically, I will retrieve all records of failed login attempts that occurred after 18:00 (6:00 PM).

## SQL Query:
~~~
SELECT *
FROM log_in_attempts
WHERE success = 0 AND TIME(login_time) > '18:00:00';
~~~
Retrieve login attempts on specific dates
To investigate a specific event, I will query the "log_in_attempts" table to retrieve login attempts that occurred on 2022-05-09 or 2022-05-08.

SQL Query:
~~~
SELECT *
FROM log_in_attempts
WHERE login_date IN ('2022-05-08', '2022-05-09');
~~~

Retrieve login attempts outside of Mexico
To examine suspicious login attempts that occurred outside of Mexico, I will use SQL filters to retrieve records from the "log_in_attempts" table where the country is not Mexico (both "MEX" and "MEXICO" should be considered).

SQL Query:
~~~
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
~~~
Retrieve employees in Marketing
To gather information about employees in the Marketing department located in the East building, I will query the "employees" table and apply SQL filters.

SQL Query:
~~~
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
~~~
Retrieve employees in Finance or Sales
To identify employees in the Finance or Sales departments, I will query the "employees" table using SQL filters.

SQL Query:
~~~
SELECT *
FROM employees
WHERE department IN ('Finance', 'Sales');
~~~
Retrieve all employees not in IT
To target all employees not belonging to the IT department, I will query the "employees" table using SQL filters.

SQL Query:
~~~
SELECT *
FROM employees
WHERE department != 'Information Technology';
~~~
Summary
Through SQL queries, I've conducted a comprehensive investigation into potential security issues, including after-hours login attempts, suspicious login attempts on specific dates, login attempts from outside Mexico, and employee details based on department and location. These queries assist in enhancing the organization's security by identifying and addressing potential vulnerabilities and risks.
