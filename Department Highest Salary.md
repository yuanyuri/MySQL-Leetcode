# MySQL-Leetcode
The Employee table holds all employees. Every employee has an Id, a salary, and there is also a column for the department Id.

+----+-------+--------+--------------+
| Id | Name  | Salary | DepartmentId |
+----+-------+--------+--------------+
| 1  | Joe   | 70000  | 1            |
| 2  | Henry | 80000  | 2            |
| 3  | Sam   | 60000  | 2            |
| 4  | Max   | 90000  | 1            |
+----+-------+--------+--------------+
The Department table holds all departments of the company.

+----+----------+
| Id | Name     |
+----+----------+
| 1  | IT       |
| 2  | Sales    |
+----+----------+
Write a SQL query to find employees who have the highest salary in each of the departments. For the above tables, Max has the highest salary in the IT department and Henry has the highest salary in the Sales department.

+------------+----------+--------+
| Department | Employee | Salary |
+------------+----------+--------+
| IT         | Max      | 90000  |
| Sales      | Henry    | 80000  |
+------------+----------+--------+

思路：要求找到每个部门中Salary最高的员工的信息。因此需要使用 max() 与 group by 的结合，找到每个部门的最高Salary, 使用子查询判断每个员工的salary是否为相应部门的最大值。

select D.Name Department, E.Name Employee, E.Salary Salary from Employee E, Department D where E.DepartmentId = D.Id and (E.DepartmentId, E.Salary) in (select DepartmentId, max(salary) from Employee group by (DepartmentId)) order by Salary
