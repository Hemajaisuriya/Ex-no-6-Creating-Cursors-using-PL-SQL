# Ex. No: 6 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```sql
CREATE TABLE employee(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10), salary NUMBER);
INSERT INTO employee VALUES(1,'Sita','HR',70000);
INSERT INTO employee VALUES(2,'Anjali','MD',95000);
INSERT INTO employee VALUES(3,'Chandhini','Finance',80000);
```
### PLSQL Cursor code
```sql
set serveroutput on
declare
cursor employee_cursor is
select empid, empname, dept, salary
from employee;
empid number;
empname varchar(90);
dept varchar(90);
salary number;
begin
open employee_cursor;
loop
fetch employee_cursor into empid,empname,dept,salary;
exit when employee_cursor%notfound;
dbms_output.put_line('Employee ID: '||empid);
dbms_output.put_line('Employee Name: '||empname);
dbms_output.put_line('Department: '||dept);
dbms_output.put_line('Salary: '||salary);
dbms_output.put_line('-x-x-x-x-x-x-x-x-x-x-x-x-x-');
end loop;
close employee_cursor;
end;
/
```
### Output:
![image](https://github.com/DHARINIPV/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119400845/15a223bf-f523-402f-a961-a9d834a2b6f4)

### Result:
Thus a cursor using PL/SQL is created successfully.
