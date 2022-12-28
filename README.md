# insurance_premium_analysis

## 1. Objective

* Exploratory Analysis of Insurance Expenses using pandas and seaborn.
* Understand which variables are more relevant for determining health insurance expenses.

## 2. Sources

[Kaggle Dataset Link](https://www.kaggle.com/code/venky12347/insurance-premium/data)

## 3. Notebooks and files

* [insurance.csv](https://github.com/IsiAlas/insurance_premium_analysis/blob/main/insurance.csv) - dataset
* [insurance_expenses_analysis.ipynb](https://github.com/IsiAlas/insurance_premium_analysis/blob/main/insurance_expenses_analysis.ipynb) - Exploratory Analysis Notebook

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

*Correlation Heatmap For Smokers*

<img src="https://user-images.githubusercontent.com/48052532/209884874-c45b99b2-a14f-4225-9041-1d93d31dcba7.png" alt="drawing" width="350"/>

For smokers we can observe that:

* age has a low positive correlation with expenses -> Corr = 0.37
* bmi has a high positive correlation with expenses -> Corr = 0.81

*Correlation Heatmap For Non-mokers*

<img src="https://user-images.githubusercontent.com/48052532/209884965-b9494609-a435-4d73-96f4-3cf29aac1a08.png" alt="drawing" width="350"/>

For non-smokers we can observe that:

* age has a moderate positive correlation with expenses -> Corr = 0.63
* bmi has no correlation with expenses --> Corr= 0.084
