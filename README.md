# dbms-assign-10

create table employee11(empid number(3),
name varchar2(25),
doj date,
jobid varchar(15),salary number(8));
insert into employee11 values(100,'Aman Jian','17-june-2017','AD_PRES',24000.00);
insert into employee11 values(101,'Yash Kumar','15-july-2019','AD_vp',17000.00);
insert into employee11 values(102,'Ayushi','12-aug-2017','IT_PROG',9000.00);
insert into employee11 values(103,'Kamal','15-sep-2016','IT_PROG',6000.00);
insert into employee11 values(104,'Madhav Mohan','14-july-2018','IT_PROG',4000.00);
insert into employee11 values(105,'Astha sharma','27-june-2017','PU_CLERK',2500.00);

SELECT * FROM employee11;
select NAME from employee11 where salary>(SELECT SALARY from employee11 where empid=104);
SELECT NAME,SALARY,JOBID from EMPLOYEE11 where JOBID=(SELECT JOBID FROM EMPLOYEE11 WHERE empid=103);



SELECT name, salary, jobid  
FROM employee11  
WHERE salary IN  
( SELECT MIN(salary)  
FROM employee11  
GROUP BY jobid 
);



SELECT * FROM EMPLOYEE11
WHERE DOJ=(SELECT DOJ FROM EMPLOYEE11
WHERE EMPID=105);

SELECT * FROM EMPLOYEE11
WHERE DOJ>(SELECT DOJ FROM EMPLOYEE11
WHERE EMPID=105);
