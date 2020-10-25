# CG-DB-Employee-Payroll
## UC1 - Create database for payroll_service
```create database payroll_service;```
### To check the creation of DB
```show databases;```
### To go to the DB created
```use payroll_service;```

## UC2 - Create a employee payroll table
```CREATE TABLE employee_payroll
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
