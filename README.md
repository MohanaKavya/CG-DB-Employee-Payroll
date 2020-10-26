# CG-DB-Employee-Payroll
## UC1 - Create database for payroll_service
```create database payroll_service;```
### To check the creation of DB
```show databases;```
### To go to the DB created
```use payroll_service;```

## UC2 - Create a employee payroll table
```
CREATE TABLE employee_payroll
    -> (
    ->   id                  INT unsigned NOT NULL AUTO_INCREMENT,
    ->   name                VARCHAR(150) NOT NULL,
    ->   salary              Double NOT NULL,
    ->   start               DATE NOT NULL,
    ->   PRIMARY KEY         (id)
    -> );
```
### To view table desciption
```DESCRIBE employee_payroll;```

## UC3 - Ability to insert employee payroll data into the table
``` 
INSERT INTO employee_payroll(name , salary , start) VALUES
    -> ( 'Bill',1000000.00,'2018-01-03'),
    -> ( 'Terisa',2000000.00,'2019-11-13'),
    -> ('Charlie',3000000.00,'2020-05-21');
```

## UC4 - Ability to retrieve all the employee payroll data
```SELECT* FROM employee_payroll;```

## UC5 - Ability to retrieve salary data of employees by their name and who have joined in a particular data range
### Viewing salary of particular person
```SELECT salary FROM employee_payroll WHERE name='Charlie';```
### Checking employees who joined at particular date range
```SELECT * FROM employee_payroll WHERE start BETWEEN CAST('2019-01-01' AS DATE) AND DATE(NOW());```

## UC6- Ability to add gender attribute to table
### Adding gender
```ALTER TABLE employee_payroll ADD gender CHAR(1) AFTER name;```
### Setting F gender for female employees
```update employee_payroll set gender = 'F' where name='Terisa' or name='Kavya';```
### Setting M gender for male employees
```update employee_payroll set gender='M' where name='Bill' or name='Charlie';```
### Viewing gender
```SELECT * FROM employee_payroll;```

## UC7 - Ability to perform Sum, Average, Min, Max, Count Operations on Table Records
### Total salary according to gender
```SELECT gender, SUM(salary) as Total_Salary FROM employee_payroll GROUP BY gender;```
### Average salary according to gender
```SELECT gender, AVG(salary) as Average_Salary FROM employee_payroll GROUP BY gender;```
### Minimum salary according to gender
```SELECT gender, MIN(salary) as Minimum_Salary FROM employee_payroll GROUP BY gender;```
### Maximum salary according to gender
```SELECT gender, MAX(salary) as Maximum_Salary FROM employee_payroll GROUP BY gender;```
### Count of employees according to gender
```SELECT gender, COUNT(salary) as Number_of_Employees FROM employee_payroll GROUP BY gender;```
