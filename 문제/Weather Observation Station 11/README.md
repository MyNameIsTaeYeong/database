## 문제 : https://www.hackerrank.com/challenges/weather-observation-station-11/problem

```
SELECT distinct CITY
FROM STATION
WHERE (LEFT(CITY,1) != 'a'
and LEFT(CITY,1) != 'e'
and LEFT(CITY,1) != 'i'
and LEFT(CITY,1) != 'o'
and LEFT(CITY,1) != 'u')
or (Right(CITY,1) != 'a'
and Right(CITY,1) != 'e'
and Right(CITY,1) != 'i'
and Right(CITY,1) != 'o'
and Right(CITY,1) != 'u')
```
