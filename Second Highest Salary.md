# MySQL-Leetcode
Write a SQL query to get the second highest salary from the Employee table.

+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
For example, given the above Employee table, the second highest salary is 200. If there is no second highest salary, then the query should return null.

思路：题目要求找第二大的数，因此使用两次max()即可。由于MySQL 的限制，在求出第一大之后，还要在使用Select 一次。

SELECT max(Salary) FROM Employee WHERE Salary < select Salary from (SELECT max(Salary) FROM Employee));
