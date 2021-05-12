## 문제 : https://www.hackerrank.com/challenges/weather-observation-station-7/problem

```
SELECT distinct CITY
FROM STATION
WHERE RIGHT(CITY, 1) = 'a'
or RIGHT(CITY, 1) = 'e'
or RIGHT(CITY, 1) = 'i'
or RIGHT(CITY, 1) = 'o'
or RIGHT(CITY, 1) = 'u'
```
