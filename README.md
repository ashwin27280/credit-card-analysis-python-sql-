# Credit-Card-Analysis

## 📌 Problem Statement
In the world of finance, predicting good clients for credit card approval is a game-changer for banks. It's the key to reducing credit risk, minimizing defaults, and ensuring a healthier credit card portfolio. This project analyzes a credit card applicant dataset to uncover the demographic, financial, and lifestyle factors that influence credit card acceptance — helping banks make smarter, data-driven approval decisions.

## 🛠️ Tools Used
- **Python** 🐍 — `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy.stats` for data cleaning, EDA, and hypothesis testing
- **SQL** 🗄️ — MySQL for structured querying and business-question analysis
- **Google Colab** — notebook environment

## 🔍 Approach
1. 📥 **Data Collection** — Merged applicant details and credit label datasets on `Ind_ID`
2. 🧹 **Data Cleaning** — Renamed columns, converted `Birthday_count`/`Employed_days` into `Age`/`Employed_years`, fixed negative-year inconsistencies, handled missing values, dropped the `Type_Occupation` column, imputed `Gender` with the mode
3. 📊 **Outlier Treatment** — Detected and capped outliers in `Annual_Income`, `Age`, and `Employed_years` using boxplots
4. 📈 **Exploratory Data Analysis (EDA)** — Studied distributions, acceptance rates, and relationships across gender, income type, marital status, education, family size, and ownership status
5. 🔗 **Correlation Analysis** — Built a heatmap to examine relationships between numerical variables and `Credit_status`
6. 🔬 **Hypothesis Testing** — Ran a one-way ANOVA (α = 0.05) to test whether annual income significantly affects credit approval
7. 🗄️ **SQL Analysis** — Answered business questions directly against the cleaned dataset (see `sql_analysis.sql`)

## 📂 Dataset
The dataset contains applicant records with 19 fields, including `Gender`, `Car_Owner`, `Property_Owner`, `Children_count`, `Annual_income`, `Type_Income`, `Education`, `Marital_status`, `Family_members`, `Age`, `Employed_years`, and `Credit_status` (target: 0 = good credit, 1 = bad credit).

## 📈 Key EDA Insights
- 88.7% of applicants were accepted for a credit card, while 11.3% were rejected
- Female applicants (63.3%) outnumber male applicants (36.7%)
- `Commercial associate` is the highest-earning income type (₹220,539 avg.), followed by `State servant`, `Working`, and `Pensioner`
- Car/property ownership shows little impact on acceptance — the acceptance rate stays around 88% regardless
- Academic degree holders have a 100% acceptance rate, though they make up a very small share of applicants
- `Credit_status` correlates positively with `Annual_income` and `Age`, and negatively with `Family_members`

## 🔬 Hypothesis Testing
**H₀:** Annual income has no effect on credit card approval
**H₁:** Annual income affects credit card approval

Using a one-way ANOVA at a 5% significance level, the p-value obtained was **0.045** (< 0.05), so the null hypothesis was rejected — **higher annual income is associated with a higher likelihood of approval.**

## 🗄️ SQL Analysis
`sql_analysis.sql` answers business questions directly on the cleaned dataset, including:
| # | Question | Key Result |
|---|----------|-----------|
| 1 | Average annual income by income type | Commercial associates earn the most (₹220,539) |
| 2 | Female owners of both car & property | 179 customers |
| 3 | Male customers living with family | 470 customers |
| 4 | Top 5 highest earners | Highest income: ₹492,750 (3 applicants) |
| 5 | Married applicants with bad credit | 140 customers |
| 6 | Highest education level & count | Academic degree — only 2 applicants |
| 7 | Bad credit % — married males vs. females | Males: 11.98% vs. Females: 9.80% |

## ✅ Final Conclusions
1. The Hypothesis Testing shows that high-income people are more likely to get credit card approval.

2. he pie chart shows that 88.7% of applicants got accepted, while only 11.3% were rejected for Credit card.

3. There are more female applicants (63.3%) than male applicants (36.7%).

4. Working in private companies makes applicants more likely to apply for a credit card, whereas State servants are less likely to apply due to income disparities. Commercial associates have higher income, followed by State servants and working professionals, while pensioners, who are non-employees, have lower income. Pensioners are typically retired and older than other groups

5. The "Working" class in private companies, due to lower income and lack of benefits provided for State servants, is most likely to apply for a credit card. Job stability also plays an important role in credit card approval, with State servants having higher stability and approval rates.

6. Ownership of a car or property doesn't significantly impact credit card approval, as the average acceptance rate is 88% for all conditions.

7. Married individuals living with family are the highest among credit card applicants, followed by single individuals. Civil marriages have the highest acceptance rate, while single individuals have the lowest acceptance rate.

8. Academic degree holders have a 100% acceptance rate, indicating that higher education levels are more likely to lead to credit card approval. However, the number of applicants with an academic degree is less compared to those with a secondary education.

9. Most families applying for credit cards are small families, and newly married individuals are more likely to apply.

10. Credit_status shows positive correlation with Annual_income and Age, while it has a negative correlation with Family_members.

The bank's main focus have to be on middle-aged working professionals to generate high revenue.



**Bottom line:** Banks should focus on middle-aged, working professionals with stable, higher incomes to build a healthier, more profitable credit card portfolio.

## 📁 Repository Structure
```
├── credit_card.ipynb      # Data cleaning, EDA, and hypothesis testing (Python)
├── sql_analysis.sql       # Business-question analysis on the cleaned dataset (SQL)
└── README.md
```

