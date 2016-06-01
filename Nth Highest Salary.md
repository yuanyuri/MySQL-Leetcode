# MySQL-Leetcode
Write a SQL query to get the nth highest salary from the Employee table.

+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
For example, given the above Employee table, the nth highest salary where n = 2 is 200. If there is no nth highest salary, then the query should return null.

思路：先按照Salary进行降序排列，再使用limit 即可。
SELECT ...[LIMIT offset_start, row_count]，其中offset_start 表示起始偏移量为0，row_count表示显示的行数。

CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
DECLARE M INT;
SET M = N - 1;
  RETURN (
      Select distinct salary from Employee  order by Salary DESC limit M,1
      
  );
END
