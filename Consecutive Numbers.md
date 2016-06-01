# MySQL-Leetcode.
Write a SQL query to find all numbers that appear at least three times consecutively.

+----+-----+
| Id | Num |
+----+-----+
| 1  |  1  |
| 2  |  1  |
| 3  |  1  |
| 4  |  2  |
| 5  |  1  |
| 6  |  2  |
| 7  |  2  |
+----+-----+
For example, given the above Logs table, 1 is the only number that appears consecutively for at least three times.
思路：表连接。用两个的作为条件来约束所要查找的表。


select distinct l1.Num ConsecutiveNums  from Logs l1, Logs l2, Logs l3 where l1.id = l2.id - 1 and l1.id = l3.id - 2 and l1.Num = l2.Num and l1.Num = l3.Num;
