# Ex. No: 5 Creating Triggers using PL/SQL

### AIM: To create a Trigger using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create salary_log table with following attributes (log_id NUMBER GENERATED ALWAYS AS IDENTITY, empid NUMBER,empname VARCHAR(10),old_salary NUMBER,new_salary NUMBER,update_date DATE);
3. Create a trigger named as log_salary-update.
4. Inside the trigger block, Insert the values into the salary_log table whenever the salary is updated.
5. End the trigger.
6. Update the salary of an employee in employee table.
7. Whenever a salary is updated for the employee it must be logged into the salary_log table with old salary and new salary.
8. Display the employee table, salary_log table.

### Program:
### Create employee table
```
 create table employee(empid int,empname varchar(25),dept varchar(20),salary int);
```
### Create salary_log table
```
 CREATE TABLE salary_log1 (log_id INT AUTO_INCREMENT PRIMARY KEY,empid INT,empname VARCHAR(10),old_salary DECIMAL(10, 2),new_salary DECIMAL(10, 2),update_date DATE);

```

### PLSQL Trigger code
```
DELIMITER //
CREATE TRIGGER log_salary_update AFTER UPDATE ON employee1 FOR EACH ROW
 BEGIN
 INSERT INTO salary_log (empid, empname, old_salary, new_salary, update_date) VALUES (OLD.empid, OLD.empname, OLD.salary, NEW.salary,NOW());
 end;
```

### Output:
![Screenshot 2023-10-05 162348](https://github.com/paulsamson18/Ex-No-5-Creating-Triggers-using-PL-SQL/assets/119405794/e2b89292-7ca8-40a6-8724-137918903990)

![Screenshot 2023-10-05 162323](https://github.com/paulsamson18/Ex-No-5-Creating-Triggers-using-PL-SQL/assets/119405794/d60aab3f-9ebe-42c5-92d7-94c8fb518206)

### Result:
Thus program executed successfully.
