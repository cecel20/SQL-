# SQL-
SQL practice Question list
Table: RequestAccepted

+----------------+---------+
| Column Name    | Type    |
+----------------+---------+
| requester_id   | int     |
| accepter_id    | int     |
| accept_date    | date    |
+----------------+---------+


Solution:
# Write your MySQL query statement below
with total_info as (
    select requester_id as id
        from RequestAccepted
union all
    select accepter_id as id
        from RequestAccepted)
select id, count(id) as num
from total_info
group by id
order by num DESC
limit 1
;

