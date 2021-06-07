## 문제 : https://www.hackerrank.com/challenges/more-than-75-marks/problem

```
SELECT Name
FROM STUDENTS
WHERE Marks > 75
order by RIGHT(Name, 3) ASC, ID ASC
```
