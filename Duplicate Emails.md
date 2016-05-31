# MySQL-Leetcode
Write a SQL query to find all duplicate emails in a table named Person.

+----+---------+
| Id | Email   |
+----+---------+
| 1  | a@b.com |
| 2  | c@d.com |
| 3  | a@b.com |
+----+---------+
For example, your query should return the following for the above table:

+---------+
| Email   |
+---------+
| a@b.com |
+---------+

思路：使用聚合函数以及group by email 即可。
trick : group by 经常与聚合函数一起使用，GROUP BY 关键字 表示要进行分类聚合的字段。
having:关键字表示对分类后的结果在进行条件的过滤。
having 与 where 的区别在于，having 是对聚合后的结果进行的条件过滤，而where是在聚合前就对纪录进行过滤。如果逻辑允许，应该尽可能用where
先过滤纪录。



code:
select Email from Person group by Email having count(*) > 1;
