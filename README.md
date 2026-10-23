# HR-ANALYTICS-DASHBOARD
This project features an interactive Power BI dashboard designed to analyze workforce performance and employee attrition using HR analytics data. The primary goal is to transform raw HR data into actionable visual insights on employee demographics, job satisfaction, department distribution, and turnover patterns.

<img width="1312" height="742" alt="image" src="https://github.com/user-attachments/assets/25d4e37d-6844-42ef-af5a-555ad6476252" />

## Business Questions Framework

| Dimension | Key Business Questions |
| :--- | :--- |
| **TCore HR KPIs** | 1. What are the total employees, active employees, attrition count, and attrition rate?   <br>2. What is the average employee age and average experience level? |
| **Department & Role** | 1. Which departments contribute the most to employee turnover?<br>2. How is total headcount distributed across departments? |
| **Demographics & Experience** | • 1. Which age groups show the highest attrition risk?<br> 2. What is the gender distribution among departing employees? <br> 3. How does attrition trend across total years of experience?  |
| **Compensation & Satisfaction** | 1. Which salary bands experience the highest attrition rate?<br> 2 How do job roles and satisfaction levels impact turnover? |

## Data Cleaning & Preparation (Power Query & DAX)
The raw dataset underwent structured cleaning and transformation in Power Query and DAX:
1. Duplicate Removal: Verified unique EmpID records and removed duplicates.
2. Missing Value Handling: Cleared and imputed missing values in critical fields.
3. Data Type Validation: Corrected field formats (e.g., set Age and TotalExperience to Whole Numbers).
4. Column Standardization: Standardized column naming for smooth DAX integration.
5. DAX KPI Measures: Created explicit DAX measures:
   a. Total Employees = COUNT(HR_Analytics[EmpID])
   b. Attrition Count = CALCULATE(COUNT(HR_Analytics[EmpID]), HR_Analytics[Attrition] = "Yes")
   c. Active Employees = CALCULATE(COUNT(HR_Analytics[EmpID]), HR_Analytics[Attrition] = "No")
   d. Attrition Rate % = DIVIDE([Attrition Count], [Total Employees], 0)
   e. Avg Age = AVERAGE(HR_Analytics[Age])
   f. Avg Experience = AVERAGE(HR_Analytics[TotalExperience(Years)])

## Visualizations Included
1. KPI Cards: Total Employees (1.403K), Active Employees (1.176K), Attrition Count (227), Attrition Rate (16.18%), Avg Age (36.97), and Avg Experience (7.05 yrs).
2. Donut Chart: Attrition share by Department (Administration 36.56%, Sales 22.03%, Operations 18.94%, IT 12.78%, Marketing 3.96%, etc.).
3. Bar Chart: Attrition vs. Active employees across Salary Slabs (6-10 LPA, 0-3 LPA, 3-6 LPA, 10+ LPA).
4. Heatmap Matrix: Attrition breakdown by Job Role and Job Satisfaction (Scale 1–4).
5. Column Chart: Employee age group distribution (18–25 to 55+).
6. Pie Chart: Attrition distribution by Gender (Male: 63.44% / 144, Female: 36.56% / 83).
7. Line Chart: Attrition trends by total years of experience.
8. Funnel Chart: Headcount distribution by Department.
9. Interactive Slicers: On-screen department slicers for dynamic filtering.

## Dataset Fields
1. EmpID / EmployeeNumber: Unique employee identifiers
2. Attrition: Employment status (Yes / No)
3. Department & JobRole: Organizational unit and specific job title
4. JobSatisfaction: Satisfaction rating (Scale 1–4)
5. Age & AgeGroup: Age data and categorized ranges (18-25, 26-35, etc.)
6. Gender: Gender classification
7. SalarySlab: Compensation tier (0-3 LPA, 3-6 LPA, 6-10 LPA, 10+ LPA)
8. TotalExperience(Years): Years of professional work experience

## Tools Used
1. Power BI Desktop: Power Query Editor, DAX Modeling, and Interactive Data Visualization
2. Microsoft Excel / CSV: Raw data source
3. GitHub: Version control, documentation, and portfolio hosting

## Key Business Insights
1. Departmental Concentration: The Administration department drives the highest turnover at 36.56% (83 employees), followed by Sales (22.03%) and Operations (18.94%).
2. Compensation Sensitivity: Employees in lower-to-mid salary tiers (0–3 LPA and 3–6 LPA) exhibit significantly higher attrition compared to higher earners.
3. Gender Disparity: Male employees account for a larger share of overall attrition (63.44%).
4. Early-Career Turnover: Attrition peaks during the early stages of total career experience (<5 years) and stabilizes after 10 years.
5. High-Risk Roles: Laboratory Technicians, Sales Executives, and Research Scientists report the highest exit counts, especially among those with lower job satisfaction levels (Scale 1–3).

## Strategic Recommendations
1. Early-Career Mentorship: Implement structured onboarding and retention programs for employees with under 5 years of experience.
2. Salary Tier Benchmarking: Review compensation packages for 0–3 LPA and 3–6 LPA bands to ensure market competitiveness.
3. Targeted Department Interventions: Conduct pulse surveys and workload assessments for Administration and Sales teams.
4. Satisfaction-Driven Career Paths: Establish clearer career advancement tracks for technical roles (Laboratory Technicians, Sales Executives) to boost job satisfaction. 
