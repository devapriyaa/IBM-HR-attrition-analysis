### **IBM HR Attrition Analysis**

**Objective**

The objective of this analysis is to identify the key drivers of employee attrition and quantify their impact on overall attrition, enabling data-driven decision-making to reduce employee turnover.

**Business Questions**

1.  What is the overall attrition rate in the organization?
2.  What factors contribute to employees leaving the company?
3.  Which departments and job roles are most affected by attrition?
4.  Which employee segments contribute the most to overall attrition risk?

**Dataset overview**

https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

-   The dataset consists of employee-level records capturing demographic details, job-related attributes, compensation, work environment, and attrition status. It is designed to analyze patterns and drivers of employee attrition.
-   Each row represents an individual employee
    -   Total employees: 1470
    -   Target variable: Attrition (Yes/No)

**Feature categories**

Demographic Information

-   Age – Employee age (numeric)
-   Gender – Male, Female
-   MaritalStatus – Divorced, Married, Single
-   DistanceFromHome – Distance between home and workplace

Education & Background

-   Education Below College College Bachelor Master Doctor
-   EducationField Human Resources, Life Sciences, Marketing, Medical, Other, Technical Degree

Job & Organization Details

-   Department – Human Resources, R&D, Sales J
-   JobRole – Includes roles such as: Sales Executive Research Scientist Laboratory Technician Manager Manufacturing Director Healthcare Representative, etc.
-   JobLevel – Scale from 1 to 5
-   EmployeeNumber – Unique identifier
-   EmployeeCount – Constant value (1 for all records)

Compensation & Salary

-   MonthlyIncome – Monthly salary DailyRate / HourlyRate / MonthlyRate – Pay-related metrics
-   PercentSalaryHike – Percentage salary increase
-   StockOptionLevel – Stock options assigned

Work Experience & Tenure

-   TotalWorkingYears – Total career experience
-   YearsAtCompany – Tenure in current company
-   YearsInCurrentRole – Time in current role
-   YearsSinceLastPromotion – Promotion gap
-   YearsWithCurrManager – Time with current manager
-   NumCompaniesWorked – Number of previous employers

Work Conditions & Behaviour

-   OverTime – Yes / No
-   BusinessTravel – Non-Travel, Travel Frequently, Travel Rarely
-   TrainingTimesLastYear – Number of training sessions attended

Satisfaction & Engagement Metrics (Scaled from 1 to 4)

-   EnvironmentSatisfaction – Low to Very High
-   JobSatisfaction – Low to Very High
-   RelationshipSatisfaction – Low to Very High
-   JobInvolvement – Low to Very High
-   WorkLifeBalance – Bad, Good, Better, Best

Performance Metrics

-   PerformanceRating (Scaled from 1 to 4) - Low, Good, Excellent, Outstanding

Data Cleaning & Preprocessing

Data cleaning and preprocessing were performed using Python to ensure data quality and reliability before analysis.

-   Missing Values Check

    -   Checked for missing values using: df.isnull().sum()
    -   Result: No missing values were found in the dataset.

-   Duplicate Records

    -   Checked for duplicate rows using: df.duplicated().sum()
    -   Result: No duplicate records were identified.

-   Unique Value Analysis

    -   Analyzed distinct values in each column using: df.nunique()

    -   This helped in:

        -   Identifying categorical vs numerical columns

        -   Understanding feature distribution

        -   Detecting constant or redundant fields

Removal of Irrelevant Columns

-   The following columns were removed as they do not contribute to analysis:

    -   EmployeeCount → Constant value (1 for all rows)
    -   EmployeeNumber → Unique identifier (no analytical value)
    -   StandardHours → Constant value
    -   Over18 → Same value across all records

-   Data Preparation for Analysis

    -   Converted categorical variables where necessary for analysis

    -   Created derived fields such as:

        -   Age Group
        -   Tenure Group

    -   Prepared data for Power BI visualization and DAX calculations

**Approach**

This analysis goes beyond simple attrition percentages by introducing an Impact Score to identify not just high-risk groups, but groups that contribute most to overall attrition.

**Key Metrics**

-   Attrition Rate

    Attrition rate=(Employee who left) / (Total employees)

-   Impact

    Impact=Segment attrition rate-Overall attrition rate

-   Population share

    Population share=(Segment size)/(Total employee)

-   Impact score

    Impact score=Impact\*Population share

**Key Findings**

-   Overall Attrition rate

![](images/Overall%20attrition%20rate%20screenshot.jpg){width="496"}

-   Top Drivers of Attrition

![](images/Top%205%20attrition%20drivers.jpg){width="519"}

Overtime, employee tenure (new joiners), and age group are the most significant drivers of attrition. Employees working overtime exhibit the highest impact on overall attrition.

-   Departments / Roles with Highest Attrition

![](images/Attrition%20rate%20by%20job%20role.jpg){width="525"}

Sales Representatives and Laboratory Technicians show the highest attrition rates among job roles, indicating potential role-specific challenges.

-   High-Risk Employee Segments

![](images/Top%20drivers%20screenshot.jpg){width="524"}

Employees who are working overtime, new to the organization, in their early career stages are at the highest risk of attrition.

**Insights**

-   Overtime is the strongest driver of attrition, contributing the highest impact at 4.08%.
-   New joiners contribute 2.74% impact, indicating onboarding or expectation gaps.
-   While Under 25 employees have the highest attrition rate, the 25–34 age group contributes more to overall attrition (1.54% vs 1.52%) due to a larger population.

**Business Implication**

-   Reduce excessive overtime through workload balancing.
-   Strengthen onboarding and early employee engagement programs.
-   Provide targeted support for early-career employees.

**Tools & Technologies**

-   Python (Data Transformation & Cleaning)
-   Power BI (Data Modelling & Visualization)
-   DAX (Calculated Measures & Impact Score)

**Conclusion**

This analysis highlights that attrition is driven not just by high-risk groups but by groups that combine risk with scale. By focusing on high-impact segments such as employees working overtime and new joiners, organizations can significantly reduce overall attrition.

## 🔗 Connect with Me

👩‍💼 **Devapriyaa B**\
[![LinkedIn](https://img.shields.io/badge/Connect%20on-LinkedIn-blue?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/devapriyaa-b-940442175/)