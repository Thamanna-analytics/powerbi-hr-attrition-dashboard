# Employee Attrition Dashboard (Power BI)

An interactive Power BI report that shows how many employees leave, why they leave, and which current employees are most at risk, with plain-language findings and recommended actions.

**Data:** IBM HR Analytics Employee Attrition dataset (sample data created by IBM, not a real company)
**Tools:** Power BI Desktop, Power Query, DAX
**Author:** Thamanna Shameer | [LinkedIn](https://linkedin.com/in/thamanna-shameer-68623338a)

---

## Business questions

1. How big is the attrition problem?
2. Why do employees leave?
3. Which current employees should managers check in with first?

## Report pages

| Page | What it shows |
|---|---|
| **Attrition Pulse** | Key numbers (1,470 employees, 237 leavers, 16.1% attrition, estimated yearly cost) and attrition by department, age, income and tenure |
| **Drivers** | Attrition by overtime, business travel, marital status and job role |
| **At-Risk Employees** | A simple risk score, a chart that checks it, and a list of current high-risk employees |
| **Data and Method** | Data source, how the score works, key findings, and limits |
| **Recommended Actions** | Four suggested actions based on the findings |

All pages have filters (department, job role, overtime), and the charts respond to each other when you click on them.

## Screenshots

![Attrition Pulse](screenshots/1_Attrition_Pulse.png)
![Drivers](screenshots/2_Drivers.png)
![At-Risk Employees](screenshots/3_At_Risk.png)
![Data and Method](screenshots/4_Data_and_Method.png)
![Recommended Actions](screenshots/5_Actions.png)

## Key findings (in this sample dataset)

- **16.1%** of employees left (237 of 1,470).
- **Overtime:** employees who work overtime left 30.5% of the time, against 10.4% without overtime. 53.6% of all leavers worked overtime, though only 28.3% of employees do.
- **Early career:** employees under 25 left 39.2% of the time, and those in their first 2 years left 34.9%.
- **Pay:** employees earning under 3,000 a month left 28.6% of the time.
- **Role:** Sales Representatives left 39.8% of the time, the highest of all roles.
- **Travel and marital status:** frequent travellers left 24.9%, and single employees left 25.5%.

## The risk score

Each employee gets 1 point for each of six risk factors: works overtime, is under 30, earns under 3,000 a month, has been at the company under 2 years, is single, and travels frequently.

| Risk level | Score | Employees | Share who left |
|---|---|---|---|
| Low | 0-1 | 866 | 6.7% |
| Medium | 2-3 | 516 | 23.1% |
| High | 4-6 | 88 | 68.2% |

Among employees who have **not** left, 28 are High risk (2.3% of 1,233 current employees). The list is meant to start supportive conversations about pay, workload and growth, not to judge people.

## What I built

- Cleaned the data in Power Query (removed 6 columns that were not needed, added an attrition flag).
- Wrote DAX measures: total employees, leavers, attrition rate, estimated attrition cost, and counts for current and high-risk employees.
- Wrote DAX calculated columns: age group, income band, tenure group, readable labels, risk score and risk level.
- Designed five report pages with a consistent colour meaning (orange = attrition), a short plain-language sentence under every chart title, and a data and method page.

## Limits

- This is **sample data**, so the results show the method, not a real company.
- The estimated cost assumes that replacing a leaver costs **50% of their yearly salary**. This is an assumption, not part of the data, and the dataset does not state the currency.
- The risk score was built and checked on the **same data**, so it would likely be less accurate on new employees.
- Some groups are small, so their rates should be read with care.
- The charts show links, not proven causes.
- The data has no dates, so trends over time cannot be shown.

## Next steps

- Test the risk score on unseen data in Python (train and test split).
- Add a cost slider so the cost assumption can be changed in the report.

## Files in this repository

| File | Description |
|---|---|
| `HR_Attrition_Dashboard.pbix` | The Power BI report (open with Power BI Desktop) |
| `HR_Attrition_Dashboard.pdf` | A PDF export of the report pages |
| `screenshots/` | Screenshots of each report page |

The original dataset is available on Kaggle: [IBM HR Analytics Employee Attrition & Performance](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset).
