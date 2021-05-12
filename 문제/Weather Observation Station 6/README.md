## 문제 : https://www.hackerrank.com/challenges/weather-observation-station-6/problem

```
SELECT distinct city
FROM station
WHERE SUBSTRING(city,1,1) = 'a' or SUBSTRING(city,1,1) = 'e' or SUBSTRING(city,1,1) = 'i' or SUBSTRING(city,1,1) = 'o' or SUBSTRING(city,1,1) = 'u'
```
