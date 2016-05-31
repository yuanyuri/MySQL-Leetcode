# MySQL-Leetcode
Employees Earning More Than Their Managers
The Employee table holds all employees including their managers. Every employee has an Id, and there is also a column for the manager Id.

+----+-------+--------+-----------+
| Id | Name  | Salary | ManagerId |
+----+-------+--------+-----------+
| 1  | Joe   | 70000  | 3         |
| 2  | Henry | 80000  | 4         |
| 3  | Sam   | 60000  | NULL      |
| 4  | Max   | 90000  | NULL      |
+----+-------+--------+-----------+
Given the Employee table, write a SQL query that finds out employees who earn more than their managers. For the above table, Joe is the only employee who earns more than his manager.

+----------+
| Employee |
+----------+
| Joe      |
+----------+
题目的要求是求出Salary大于其Managers 的 人员信息。
思路：使用表连接。
使用它内链接 ManagerId 与 Id 进行连接得到一个新的表。

select a.Name Employee from Employee  a, Employee  b where a.ManagerId = b.ID and a.Salary > b.Salary;
