# Business Recommendations

The analysis identified several customer segments and behavioral patterns associated with higher churn. Based on the EDA, SQL analysis, and machine learning results, the following recommendations can be considered for customer retention.

## 1. Focus on Early-Tenure Customers

Churn is substantially higher among customers in their early months of tenure. The SQL analysis shows churn of **52.94% for customers with 0–6 months of tenure**, compared with only **9.51% for customers with 49+ months**.

**Recommendation:**

* Introduce a structured onboarding program for new customers.
* Conduct proactive check-ins during the first few months.
* Provide easy access to technical and customer support.
* Monitor newly acquired customers more closely using the ML churn probability.

The first few months should be treated as an important retention window.

---

## 2. Prioritize Month-to-Month Customers

Month-to-month customers have a churn rate of **42.71%**, compared with **11.27% for one-year contracts** and **2.83% for two-year contracts**.

The SQL analysis also shows that the **Month-to-month + Fiber optic** segment has a **54.61% churn rate** and the largest churn-associated monthly revenue.

**Recommendation:**

* Identify high-probability churn customers on month-to-month contracts.
* Offer suitable contract upgrade incentives where commercially appropriate.
* Communicate the benefits of longer-term plans.
* Combine contract information with ML churn probability rather than targeting every month-to-month customer equally.

---

## 3. Address the Electronic Check Segment

Electronic check users have a churn rate of **45.29%**, compared with approximately **15–17%** for automatic bank transfer and credit card payments.

Within month-to-month contracts, electronic check users have a churn rate of **53.73%**.

**Recommendation:**

* Encourage customers to adopt automatic payment methods.
* Simplify the process of changing payment methods.
* Provide reminders and educational communication around automatic billing.
* Give additional attention to customers who combine electronic check payment with high predicted churn probability.

This recommendation should be treated as a retention hypothesis to test rather than assuming that payment method itself causes churn.

---

## 4. Investigate Fiber Optic Customer Experience

Fiber optic customers have a churn rate of **41.89%**, compared with **18.96% for DSL** and **7.40% for customers without internet service**.

Among fiber customers who churned, the recorded reasons include competitor offers, higher competitor speeds, service/support issues, price concerns, and network reliability.

**Recommendation:**

* Investigate network reliability and service-quality complaints among fiber customers.
* Monitor competitor speed and offer positioning.
* Review support interactions for high-risk fiber customers.
* Identify whether high monthly charges are accompanied by lower perceived value.
* Prioritize high-risk fiber customers for proactive service-quality outreach.

The analysis identifies these as areas for investigation; it does not establish a single causal reason for fiber churn.

---

## 5. Strengthen Customer Support and Service Experience

The recorded churn reasons show substantial numbers of customers leaving because of **support/service attitude issues**. Competitor-related reasons were also prominent in the churn-reason analysis.

**Recommendation:**

* Monitor customer support complaints and unresolved issues.
* Improve escalation processes for recurring service problems.
* Provide targeted follow-up after major support interactions.
* Combine support-related information with churn probability when prioritizing retention activities.

Improving customer experience may be particularly relevant for customers who are already showing elevated predicted churn probability.

---

## 6. Use Risk-Based Retention Prioritization

The Random Forest model generates a churn probability for active customers. Based on the business-defined risk thresholds used in the project:

* **High Risk:** 610 customers
* **Medium Risk:** 1,066 customers
* **Low Risk:** 3,498 customers

High- and Medium-Risk customers together represent **1,676 active customers** and approximately **$123,247.30 in monthly charges**.

**Recommendation:**
Create a risk-based retention workflow:

**High Risk → Immediate review**
**Medium Risk → Proactive engagement**
**Low Risk → Normal customer engagement**

This allows retention resources to be focused on customers with higher predicted churn probability instead of treating the entire customer base equally.

---

## 7. Combine Churn Probability with Customer Value

The analysis shows that churn probability and customer value do not necessarily move together. High-risk customers had the lowest average CLTV among the three risk groups.

**Recommendation:**
Use two dimensions when prioritizing retention:

**Churn Probability + Customer Value**

For example, the business can create a retention priority matrix:

| Churn Probability | Customer Value | Suggested Action                    |
| ----------------- | -------------- | ----------------------------------- |
| High              | High           | Highest-priority retention review   |
| High              | Low            | Targeted/low-cost retention         |
| Medium            | High           | Proactive engagement                |
| Medium            | Low            | Automated or standard engagement    |
| Low               | High           | Loyalty and relationship management |
| Low               | Low            | Standard customer service           |

This provides a more practical framework than using churn probability alone.

---

## 8. Increase Service Adoption Carefully

The SQL analysis found that churn does not decrease in a simple linear way with the number of add-on services. Customers with exactly one add-on had a **38.85% churn rate**, compared with **29.75% for customers with no add-ons**, while churn decreased substantially among customers with two or more add-ons.

**Recommendation:**

* Investigate which specific services are associated with stronger customer retention.
* Avoid assuming that simply adding more services will reduce churn.
* Consider targeted service bundles where customer needs justify them.
* Test service-bundling strategies through controlled retention campaigns.

The relationship should be validated through further experimentation before treating additional services as a direct churn-reduction mechanism.

---

## 9. Build a Proactive Retention Dashboard

The Power BI dashboard can be used as an operational monitoring tool rather than only a reporting dashboard.

**Recommended monitoring areas:**

* Overall churn rate
* Churn-associated monthly revenue
* Contract-level churn
* Tenure-level churn
* Payment-method churn
* Risk-tier distribution
* High-risk customer count
* High-risk customer monthly charges
* Individual customer churn probability
* Customer CLTV

The exported `top_risk_customers.csv` can provide a starting point for reviewing the highest-risk active customers.

---

## 10. Measure Retention Actions Through Testing

The recommendations above should be treated as business actions or hypotheses to test rather than guaranteed solutions.

For future implementation, the company could compare:

* Customers receiving a retention offer vs. customers not receiving one.
* Different onboarding approaches.
* Automatic-payment conversion campaigns.
* Fiber service-quality interventions.
* Contract upgrade campaigns.

The effectiveness of each intervention should be measured using outcomes such as **retention rate, churn reduction, revenue retained, and campaign cost**.

---

# Overall Recommendation

The analysis suggests that retention efforts should move from a **broad, one-size-fits-all approach toward targeted, risk-based customer engagement**.

The strongest areas identified in this project are:

1. **Early-tenure customers**
2. **Month-to-month customers**
3. **Month-to-month + Fiber optic customers**
4. **Electronic check users**
5. **Customers with high predicted churn probability**
6. **Customers combining high churn probability with meaningful customer value**

The final objective is to connect the project's four analytical stages:

**EDA → Identify churn patterns**
**SQL → Quantify business impact**
**Machine Learning → Predict individual churn probability**
**Power BI → Monitor and prioritize retention actions**

This creates a complete **Customer Churn & Retention Analytics** workflow that moves beyond describing churn and provides a structured basis for targeted retention decisions.
