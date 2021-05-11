## 문제 : https://www.hackerrank.com/challenges/weather-observation-station-5/problem

```
select city, length(city)
from station
where length(city) = (select min(length(city)) from station)
order by city asc
limit 1;

select city, length(city)
from station
where length(city) = (select max(length(city)) from station)
order by city asc
limit 1;

```
