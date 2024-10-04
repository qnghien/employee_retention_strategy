# Employee Retention Analysis: Insights and Strategies
![Fraud Detection Image](img/emp_retention.png)

For better experience with notebook, please visit this link from RPubs: https://rpubs.com/ryanngx217/1228148
## Introduction

In today’s fast-paced work environments, retaining employees has become a top priority for organizations worldwide. When a team member leaves the company, it not only disrupts workflows but also increases costs associated with recruitment, training, and the time needed for new hires to integrate with existing teams, leading to a decrease in overall productivity. As the demand for tackling this challenge rises, many companies are turning to sophisticated analytical methods to uncover the underlying reasons behind employee turnover and to develop predictive models that anticipate future departures.

In this project, I focus on using **Survival Analysis** to address the problem of employee retention. Survival Analysis has advantages in modeling an employee’s risk of quitting, capturing time-to-event data in a way that traditional logistic regression cannot. The analysis is based on a real-world dataset provided by Edward Babushkin, which allows for a deep dive into employee turnover and offers actionable insights for improving retention strategies.

### Dataset Overview

The dataset includes the following variables:

- **experience (exp)**: Employee experience in years (renamed from 'stag').
- **event**: Employee turnover (1 = turnover, 0 = no turnover).
- **gender**: Employee’s gender (f: Female, m: Male).
- **age**: Employee’s age (in years).
- **industry**: Employee’s industry sector.
- **profession**: Employee’s profession.
- **traffic**: The source or pipeline through which the employee came to the company:
  - **advert**: Applied directly after seeing ads or company branding.
  - **recNErab**: Came through a non-employee friend’s recommendation.
  - **referal**: Recommended by an employee friend.
  - **youjs**: Applied for a vacancy on a job site.
  - **KA**: Recruited through an agency.
  - **friends**: Invited by the employer through prior acquaintance.
  - **rabrecNErab**: Employer contacted via non-employee recommendation.
  - **empjs**: Found by the employer through a resume on a job site.
- **coach**: Presence of a coach or training during probation (1 = yes, 0 = no).
- **head_gender**: Gender of the employee’s supervisor.
- **greywage**: Whether the salary is reported to tax authorities (grey wage system).
- **way**: Employee’s mode of transportation to work.
- **extraversion**: Employee’s extraversion score.
- **independ**: Employee’s independence score.
- **selfcontrol**: Employee’s self-control score.
- **anxiety**: Employee’s anxiety score.
- **novator**: Employee’s innovation (novator) score.

---

## Methods Used:

1. **Non-parametric**: Kaplan-Meier with log-rank test to assess significant differences in retention rates for various features.
2. **Parametric**: Accelerated Failure Time (AFT) model using Weibull distribution for best-fit survival estimates.
3. **Semi-parametric**: Cox Proportional Hazards model with stratification by profession to meet the proportional hazards assumption.
4. **Uplift Models**: Pseudo-experiments to evaluate the effect of the following variables on retention:
   - Industry sector.
   - Profession.
   - Route to company.
   - Wage with tax-authorized compliance.
   - Mode of transportation.

---

## Summary and Conclusion
Based on a comprehensive analysis using these survival models, several key factors influence employee retention, offering valuable insights for HR leaders to develop targeted strategies to reduce turnover.

---

## Key Findings and Recap

### Industry Sector & Profession:
- **IT Employees**: Tend to stay 2.2x longer compared to those in **Finance**.
- **HR & Administration**: Lower turnover rates across all models.
- **Technical & Engineering**: Commuting by car or bus correlates with lower turnover, indicating potential job satisfaction and alignment with expectations.

### Hiring Source (Route to Company):
- **Jobsite Applications/Resume Submissions**: Employees hired through these routes have a 54% to 100% higher risk of quitting, suggesting issues with job fit or commitment.
- **Referral Programs**: Strong retention benefits, particularly for **HR & Administration** and **Technical & Engineering** roles, where referred employees are significantly less likely to quit.

### Wage Structure (Tax Compliance):
- Employees receiving **white wages (tax-authorized)** have a 37.5% lower risk of quitting compared to those paid under grey wages. Legal wage structures offer better job security and benefits, enhancing retention.

### Mode of Transportation:
- **Walkers**: Tend to have shorter tenures or higher turnover.
- **Bus Commuters**: Especially in **HR & Administration**, are more stable.
- **Car Commuters**: Among **Technical & Engineering** roles, this group is less likely to quit, suggesting these employees might benefit from tailored retention programs or incentives.

### Psychological Scores:
- **Self-Control**: Each unit increase in self-control decreases the risk of quitting by 6.3%. Programs on self-management, goal-setting, or mentoring may help retain employees with high self-control.
- **Anxiety**: Interestingly, employees with higher anxiety scores are less likely to quit, possibly due to fear of change or job insecurity. Mental health and stress management programs can further support these employees.

---

## Insights from Uplift Models (Pseudo-Experiment)

### Referral Programs:
- Highly effective for **HR & Administration** and **Technical & Engineering** roles but less so for **Sales, Marketing**, and **Management**. Strengthening referral incentives for these critical roles could improve long-term retention.

### Mode of Transportation:
- **Bus Commuters in HR & Administration**: Show better job satisfaction and are less likely to quit. Transportation-related benefits like subsidized bus passes could further enhance retention.

### Psychological Scores:
- **Self-Control & Anxiety**: Non-bus commuters with higher self-control and anxiety are less likely to quit. Understanding their personal circumstances and offering tailored support could further reduce turnover.

---

## Suggestions and Recommendations

- **Expand Referral Programs**: Particularly for **Technical & Engineering**, **HR**, and **Administration** roles, where referred employees are significantly less likely to quit.
- **Legal Wage Structure**: Ensure employees receive tax-authorized (white) wages to offer better job security and benefits, promoting retention.
- **Improve Hiring Routes**: Employees hired via job sites have significantly higher turnover. Screening processes, onboarding, or better pre-hire alignment should be considered to reduce mismatches. Strengthen referral programs with targeted incentives.
- **Support Bus & Transportation Subsidy Programs**: Employees commuting by bus, especially in **HR**, are more stable. Consider offering transportation benefits like bus subsidies or carpool options to further support these employees.
- **Promote Mental Health Programs**: Given the positive effects of self-control on retention and the association of anxiety with lower turnover, mental health support, such as counseling and stress management workshops, should be promoted to enhance employee well-being and retention.

