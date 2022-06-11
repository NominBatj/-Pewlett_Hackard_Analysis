# Pewlett Hackard Analysis
## Purpose of the Analysis
The goal of this project is to analyze a large amount of employee data for a company with more than 300,000 employees and to help Pewlett-Hackard face the "silver tsunami", which means that large number of employees are reaching retirement age. Pewlett Hackard is reviewing its workforce metrics, namely retirement, and needs help processing data that will help us understand who may be eligible for retirement and to participate in the mentorship program.
## Results
Following are results of our analysis:

### Employees Eligible for Retirement


- 90,398 (30.13%) out of 300,024 employees within the company are eligible for retirement.
- Senior Engineer, Senior Staff and Engineer's hold the largest share (23.9%) of employees likely preparing for retirement.

<img width="141" alt="query_schema_1" src="https://user-images.githubusercontent.com/66500222/172989480-ea5af0b3-a703-429b-9005-56eac3d16a9b.png">

- The departments with the highest number of potential retirees are Development(25.45%),Production(22.30%) and Sales(7.27%).

<img width="170" alt="query_schema_6" src="https://user-images.githubusercontent.com/66500222/172989606-c2480f4b-6b44-4159-aff6-9b38afab399a.png">

### Employees Eligible for Mentorship

- Only 1549 total employees qualify for mentorship/training for an internal promotion.

<img width="170" alt="query_schema_7" src="https://user-images.githubusercontent.com/66500222/172989882-c5c085da-e5b1-4b5e-96d8-efdd71ab7e5a.png">


## Summary

- How many roles will need to be filled as the "silver tsunami" begins to make an impact?

According to the analysis 72,458 roles need to be filled before retirement process.  The code below can be used to calculate the total number of employees that are about to retire.

```
select sum (count)
from retiring_titles
```

- Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

The number of competent employees who could be mentored is much smaller, just 1,549 personnel, implying that there will be enough qualified retirement-ready employees who could mentor the next generation. Following is the query to pull a table.

```
select count (title), title
from mentorship_eligibility
group by title
order by count desc;
```
