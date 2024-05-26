# Employee Attrition Analysis --[Human Resource]

_____________________________________________________

### Tools Used:-
--------------------------

1. Power Bi: For data visualization and interactive dashboards.
   
2. MySQL: For database management and data querying.
   
3. MS Excel: For data cleaning and analysis.
   
4. MS Word: For documenting findings and creating reports.

---------------------------
### TABLE OF CONTENTS:-
__________________________

- [KPI'S REQUIREMENT](#kpis-requirement)
- [CHARTS REQUIREMENT](#charts-requirement)
- [EMPLOYEE ATTRITION SQL QUERIES](#employee-attrition-sql-queries)
- [EMPLOYEE ATTRITION CHARTS](#employee-attrition-charts)
- [DASHBOARD](#dashboard)
- [CONCLUSION](#conclusion)
- [IDENTIFYING POTENTIAL REASONS FOR ATTRITION- AN ANALYTICAL OVERVIEW](#identifying_potential_reasons_for_attrition_an_analytical_overview)
- [STRATEGIES TO MITIGATE EMPLOYEE ATTRITION IN THE COMPANY](#strategies-to-mitigate-employee-attrition-in-the-company)


---------------------------
### PROBLEM STATEMENT:-
___________________________

In response to a persistent attrition rate of approximately 15% over recent years, a growing
company seeks to address the significant impact this trend has on various aspects of its
operations. With a commitment to understanding the underlying reasons for employee
departures and mitigating attrition, the company has engaged an HR analytics consultancy. As
an HR analyst spearheading this initiative, my task is to leverage available data to develop a
comprehensive dashboard. This dashboard aims to empower the organization with actionable
insights, facilitating data-driven decision-making strategies to eGectively reduce attrition and
foster a more sustainable workforce environment.

---------------------------
### KPI’S REQUIREMENT
_______________________

#### 1. Total Employees:-

• The total number of employees currently employed, providing an overview of workforce
size for resource allocation and capacity planning.

• Count unique employee IDs.


#### 2. Total Attrition:-

• The total number of employees who have left, indicating turnover extent and its impact
on operations and morale.

• Count employees with attrition status "Yes".


#### 3. Attrition Percentage:-

• Percentage of employees who have left relative to total, oGering a standardized measure
for assessing organizational health and retention eGorts.

• (Total Attrition / Total Employees) * 100



#### 4. Average Age:-

• Average age of employees, guiding recruitment strategies and providing insights into
generational understanding.

• Calculate mean age.



#### 5. Average Monthly Income:-

• Average monthly income, evaluating compensation structure and competitiveness.

• Calculate mean income.



#### 6. Average Monthly Salary:-

• Average monthly salary (including benefits), assessing remuneration package and aiding
in budget planning.

• Calculate mean salary.

---------------------------
### CHARTS REQUIREMENT
_________________________

#### 1. Attrition Count by Job Role:-

• Count of employees who left by job role, identifying departments for targeted
interventions and training.

• Count attrition by role.

#### 2. Attrition Count by Gender:-

• Count of employees who left by gender, guiding diversity initiatives and informing
retention strategies.

• Count attrition by gender.

#### 3. Attrition Count by Marital Status:-

• Count of employees who left by marital status, informing work-life balance policies and
engagement initiatives.

• Count attrition by marital status.


---------------------------
### EMPLOYEE ATTRITION SQL QUERIES
___________________________

### KPI’S VALUES:-

#### 1. Total Employees:-
```
select sum(employeecount) as Total_Employees from hr_analytics;
```

<img width="156" alt="Screenshot 2024-05-26 at 2 31 31 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/3f4b60b8-ddf8-4209-9b7b-35c9591770a8">

#### 2.Total Attrition:-
```
select sum(`A:ri6on count`) as Total_Attrition from hr_analytics;
```
<img width="154" alt="Screenshot 2024-05-26 at 2 31 54 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/5762f4e5-7cad-41b6-99c8-fdb003b6c0f0">

#### 3. Attrition Percentage:-
```
select cast(sum(`A:ri6on count`)*100 / count('employeecount')as decimal (10,2)) as
Attrition_Percentage
from hr_analytics;
```
<img width="169" alt="Screenshot 2024-05-26 at 2 32 22 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/50cb4572-49bb-40eb-b784-b1466464fb0f">

#### 4. Average Age:-
```
select cast(avg(age)as decimal (10,2)) as Average_Age from hr_analytics;
```
<img width="154" alt="Screenshot 2024-05-26 at 2 32 52 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/b47e7cd3-2a9c-4187-868e-6b92cbf8c187">

#### 5. Average Monthly Income:-
```
select cast(avg(MonthlyIncome) as decimal(10,2)) as Avg_MonthlyIncome
from hr_analytics;
```
<img width="203" alt="Screenshot 2024-05-26 at 2 33 22 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/11c2d8bc-c738-4356-ac15-ff80a77ca565">

#### 6. Average Year at Company:-
```
select cast(avg(yearsatcompany) as decimal (10,2)) as Average_YearatCompany
from hr_analytics;
```
<img width="194" alt="Screenshot 2024-05-26 at 2 33 44 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/65039bd8-c9ab-4159-91a0-75c44de5bb0f">

---------------------------

<img width="646" alt="Screenshot 2024-05-26 at 2 34 07 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/3e49e80b-dc71-44dc-b248-31eaa22cf774">


---------------------------
### EMPLOYEE ATTRITION CHARTS
________________________

#### 1. Attrition Count - Job Role:-
```
select jobrole, cast(sum(`a:ri6on count`) as decimal (10,2)) as Attrition_Count
from hr_analytics
group by jobrole
order by Attrition_Count desc;
```

<img width="272" alt="Screenshot 2024-05-26 at 2 41 57 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/f94d0265-0080-4481-9409-54d7597785c6">

<img width="485" alt="Screenshot 2024-05-26 at 2 42 33 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/3358e76f-11cd-478a-81f4-8c0a466d42c9">

---------------------------

#### 2. Attrition Count - Gender:-
```
select gender as Gender, sum(`a:ri6on count`) as Attrition_Count
from hr_analytics
group by gender
order by Attrition_Count desc;
```

<img width="185" alt="Screenshot 2024-05-26 at 2 43 34 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/cdfea1f5-0266-4800-a6ee-d2a9ffb319fa">

<img width="503" alt="Screenshot 2024-05-26 at 2 43 55 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/39a20f28-9e1a-4ee8-9940-afaff33e2725">

---------------------------------

#### 3. Attrition Count - Marital Status:-
```
select MaritalStatus, sum(`a:ri6on count`) as Attrition_Count
from hr_analytics
group by MaritalStatus
order by Attrition_Count desc;
```

<img width="235" alt="Screenshot 2024-05-26 at 2 44 50 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/7ac42d9b-f9e7-451b-9206-3865abfe32bf">

<img width="465" alt="Screenshot 2024-05-26 at 2 45 11 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/a4baca25-9bc1-48a7-b1f8-f6e12ba07721">

---------------------------

#### 4. Attrition Count – Job Satisfaction:-

<img width="489" alt="Screenshot 2024-05-26 at 2 46 04 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/1150a68f-7ef9-4561-80cc-61cb598ce64c">


---------------------------

#### 5. Attrition Count – Age:-
```
SELECT
AgeGroup,
SUM(CASE WHEN a:ri6on = 'yes' THEN 1 ELSE 0 END) AS Attrition_yes
FROM hr_analytics
GROUP BY AgeGroup
ORDER BY Attrition_yes desc;
```
<img width="240" alt="Screenshot 2024-05-26 at 2 46 39 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/8b0bd826-e982-445d-be5b-521b4d166e41">

<img width="508" alt="Screenshot 2024-05-26 at 2 47 00 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/375ac80e-5a38-4ff8-b604-28dec8bd1778">


----------------
### Dashboard 
________________

<img width="600" alt="Screenshot 2024-05-26 at 2 47 42 PM" src="https://github.com/suraj-kumar-jha/Employee_Attrition_Analysis-Human_Resource---Power-BI_Project/assets/155900363/c58e8104-0504-4c30-b68e-258a1b6a7b25">

-------------------
### CONCLUSION
___________________

Þ The project analyzed employee attrition within the organization, comprising a total of 1470
employees, with an attrition rate of 16.12%, resulting in 237 employees leaving the
company.

Þ Laboratory Technicians and Sales Executives were the most aGected job roles, with 62 and
57 employees leaving, respectively.

Þ Male employees accounted for a higher proportion of attrition compared to females, with
150 males leaving compared to 87 females.

Þ Attrition based on marital status indicated that single employees had the highest attrition
count, followed by married and divorced employees.

Þ The average age of employees aGected by attrition was 36.92 years, with an average monthly
income of $6503.

Þ On average, employees who left the company had spent approximately 7.01 years at the

-------------------------------------------
### IDENTIFYING POTENTIAL REASONS FOR ATTRITION- AN ANALYTICAL OVERVIEW
___________________________________________

Þ Implement targeted marketing campaigns during peak months (February and November) to capitalize on increased consumer spending.

Þ Enhance the online sales channel by investing in website optimization, digital advertising, and user experience improvements to better compete with offline sales.

Þ Conduct market research to identify emerging trends and consumer preferences in cosmetics, office products, and household items, and develop innovative product offerings to drive sales and profitability.

Þ Explore cost-saving measures and supply chain optimizations to reduce total costs, particularly in regions with high expenditures such as Sub-Saharan Africa.

Þ Expand market presence and distribution networks in Sub-Saharan Africa and Europe through strategic partnerships, localized marketing strategies, and tailored product o=erings to maximize revenue potential.

Þ Continuously monitor sales data, customer feedback, and market trends to identify opportunities for further optimization and refinement of sales and profitability strategies.

-------------------------------------------
### STRATEGIES TO MITIGATE EMPLOYEE ATTRITION IN THE COMPANY
___________________________________________

Þ Implement regular employee engagement initiatives such as team-building activities,
recognition programs, and career development opportunities to foster a positive work
culture and enhance job satisfaction.

Þ Conduct regular employee feedback surveys to understand their concerns, needs, and
areas for improvement, and take proactive measures to address any issues identified.

Þ Provide competitive compensation and benefits packages, including salary increases,
performance bonuses, and opportunities for advancement, to recognize and reward
employees for their contributions and encourage long-term commitment to the
organization.

Þ OGer flexible work arrangements, such as remote work options or flexible scheduling, to
accommodate employees' work-life balance needs and improve overall job satisfaction and
retention.


--------------------------******************************-----------------------------


