# insurance_expenses_analysis

## 1. Objective

* Exploratory Analysis of Insurance Expenses using pandas and seaborn.
* Understand which variables are more relevant for determining health insurance expenses.

## 2. Sources

[Kaggle Dataset Link](https://www.kaggle.com/code/venky12347/insurance-premium/data)

## 3. Notebooks and files

* [insurance.csv](https://github.com/IsiAlas/insurance_premium_analysis/blob/main/insurance.csv) - dataset
* [insurance_expenses_analysis.ipynb](https://github.com/IsiAlas/insurance_expenses_analysis/blob/main/insurance_premium_analysis.ipynb) - Exploratory Analysis Notebook

## 4. Dataset

This dataset has 1338 records with 7 features.

**Numeric variables:**
- age 
- bmi (body mass index)
- children (number of children)
- expenses (insurance)


**Categorical variables:**
- sex (male, female)
- smoker (yes, no)
- region (southwest, southeast, northwest, northeast)

## 5. Results

<img src="https://user-images.githubusercontent.com/48052532/209882567-e04d5ccd-a693-4a5a-93c4-ab7fee3d0650.png" alt="drawing" width="850"/>


* Expenses distributed very similarly between sexes. The range of expenses is practically the same between them;  0 to 60.000+

* Age has a moderate but consistent effect on expenses increase.

* Expenses increase significantly when people are smokers, regardless of age.

* In both sexes there are three distinct groups:

  - Expenses between 0 - 17.000 that increase consistently with age and are uniquely non-smokers.
  - Expenses between 10.000 - 35.000 that increase more dispersley with age and are smokers and non-smokers in similar proportion.
  - Expenses between 32.000 - 60.000+ that increase more dispersley with age and are exclusively smokers.

---

<img src="https://user-images.githubusercontent.com/48052532/209882931-09b43947-0f41-406c-851d-eb71288f4f5f.png" alt="drawing" width="850"/>

For non-smokers bmi is not impactful on the level of health expenses, whereas for smokers the higher bmi higher expenses.

---

<img src="https://user-images.githubusercontent.com/48052532/209883476-16d0dc2e-9248-4151-943b-50b4a8c3e9c9.png" alt="drawing" width="650"/>

When comparing the 4 scatterplots we can conclude the following:

* In general, non-smokers regardless of BMI classification have lower expenses than smokers.
* For underweight, healthy and overweight people health expenses can increase 2x - 10 x in the same age range if they are smokers.
* Obese people that smoke have the highest health expenses (over 30.000) and it can be 3x - 40x higher on the same age range compared to non-smokers that are obese.

---
#### Cumulative Density Function

<img src="https://user-images.githubusercontent.com/48052532/209883752-a01652a8-66c0-4814-8ced-4aec5aac8ae2.png" alt="drawing" width="850"/>

Through the graph we can observe that non-smokers have a range of expenses between aprox. 1.000 and 37.000 while smokers have a range between 13.000 and 65.000.

We can also conclude that 65%+ of the non-smokers have less than 10.000 on health expenses, while 45%+ of smokers have expenses below 30.000.

---
#### Cohen Effect Size

Effect size of expenses between smokers and non-smokers. 

Cohen's d =  3.16

There is a huge difference between group means when it comes to expenses. A 3.1 Cohen Effect Coefficient can be interpreted that smokers have an average of health expenses 3.1 standard deviations higher than non-smokers.

* Smokers average health expenses: 32,050.23
* Non-smokers average health expenses: 8,440.66

---
#### Correlation

We will use the Spearman correlation, as the more relevant correlations are for variables that have outliers and/ or don't distribute similar to normal.

Let's remember that both 'expenses' and 'BMI' have outliers that we did not drop. Even though BMI does distribute similar to normal, 'expenses' has a significant left skew while 'age' has a more uniform distribution.

**Spearman Correlation Heatmap For Smokers**

<img src="https://user-images.githubusercontent.com/48052532/210006999-5f2c6acb-81ab-40ad-b7bd-54fa51f82b7c.png" alt="drawing" width="350"/>

For smokers we can observe that:

* age has a **moderate** positive correlation with expenses -> Corr = 0.45
* bmi has a **strong** positive correlation with expenses. -> Corr = 0.83

**Spearman Correlation Heatmap For Non-smokers**

<img src="https://user-images.githubusercontent.com/48052532/210007086-a1087d5c-e880-495d-9a2b-4332a9d8a56d.png" alt="drawing" width="350"/>

For non-smokers we can observe that:

* age has a **strong** positive correlation with expenses -> Corr = 0.82
* bmi has **negligible** correlation with expenses -> Corr= 0.11

## 6. Conclusions

Smoker status has the biggest significant effect on health expense increase, with smokers having on average 4 times higher expenses.

| Smoker Status    | Average Health Expenses |
| -------------    | ------------------------|
| Smoker           | $32.050,23              |
| Non-smoker       | $8.440,66               |

Age and BMI has a low effect on health expenses in the group as a whole, but when we separate smokers and non-smokers we observe the following:
* For non-smokers age has a more significant effect on increased expenses. People older than 51 years old have almost double health expenses on average than people 30 years or younger.

| Age Group    | Average Health Expenses |
| -------------| ------------------------|
| 18 - 30      | $9.415,06               |
| 31 - 50      | $13.280,77              |
| 51 - 64      | $18.084,99              |


* For smokers BMI has the most significant effect. In this case for obese people health expenses almost doubles compared to the other BMI classifications.

| BMI Class     | Average Health Expenses |
| ------------- | ------------------------|
| Obese         | $41.557,99              |
| Overweight    | $22.495,87              |
| Healthy       | $19.942,22              |
| Underweight   | $18.809,83              |
