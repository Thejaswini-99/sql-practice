
Query Fundamentals:

select country,population from countries

where is a filter:
select * from countries where region='America'
  
Logical Operators:

select * from countries where area>5000000
SELECT * FROM countries WHERE population > 5000000 OR area > 5000000;
select * From countries where region <> 'Asia'


Order by:
It is used to arrange the elements in the order either by desc or asc
select country,region,population from countries order by population asc limit 2

Distinct:
It fetches the assiciated unique field
select distinct region as unique_region from countries


Filtering Essentials:

Not Null:
select * from users where city IS NOT NULL

Null:
select * from users where city IS NULL

In:
It fethces from the cities which fall under delhi and chennai
select * from users where city IN ('Delhi','Chennai')

select * from users where city NOT IN ('Delhi','Chennai')


Between:

select * from users where signup_at_utc NOT BETWEEN '2025-12-01 00:00:00'
                        AND '2025-12-31 23:59:59'; 


Like:
It is generally used to fetch the fields that matches with the pattern

this one whatever it starts with but need to fetch feilds from email with gmail.com
select * from users where email like '%gmail.com'

this one whatever it ends with but need to fetch feilds from email with start test
select * from users where email like 'test%'


this one fetches the fileds with _ or one charcter as we are using _
SELECT 
  id,
  email
FROM users
WHERE email LIKE 'test_user%';



\_ this one fetches the feilds with only underscore in the middle

SELECT 
  id,
  email
FROM users
WHERE email LIKE 'test\_user%';



LIMIT

Restricts the number of rows returned.
LIMIT 10

OFFSET
Often paired with LIMIT.
LIMIT 10 OFFSET 20;
Useful for pagination.
