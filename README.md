# Pay-Isn-t-the-Problem-IBM-Employee-Attrition-Analysis
Identifying drivers of voluntary attrition at IBM and modeling self-funding interventions. Pay isn't the problem.

Analysis of IBM's voluntary attrition (16.1%, ~2× the tech benchmark) using descriptive statistics, logistic regression, and policy simulation. Identifies workload, career stage, and engagement as the three independent drivers — and finds that pay drops out as a standalone factor due to its 0.95 correlation with job level. Recommends a 75% overtime reduction plus accelerated L1→L2 promotion, projected to cut attrition to 11.8% with $0.39M in net annual savings.

IBM's voluntary attrition rate (16.1%) is approximately 2× the U.S. tech sector benchmark, costing an estimated $9.25M annually. This project investigates why employees leave and models which interventions are self-funding on a total-cost basis.

Approach. Descriptive analysis of attrition patterns across department, role, level, tenure, and compensation, followed by a multivariate logistic regression with SMOTE class balancing to identify drivers that hold up after controlling for confounders, followed by a Monte Carlo simulation of four combined policy interventions.

Key finding. Three drivers each independently predict attrition: workload (overtime), career stage (job level + role tenure), and engagement (job involvement + relationship satisfaction). Compensation drops out of the final model — pay is correlated with job level at r=0.95 and is addressed through the career stage lever rather than as a separate driver.

Recommendation. A 75% overtime reduction paired with accelerated L1→L2 promotion (1 year). Projected to reduce attrition from 16.1% to 11.8% — below the U.S. cross-industry benchmark — with $0.39M in net annual savings under a salaried-exempt workforce assumption.

Stack. Python · pandas · scikit-learn · imbalanced-learn (SMOTE) · matplotlib · numpy
