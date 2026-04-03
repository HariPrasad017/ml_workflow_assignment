# Task 1 — Label and Data Leakage

Alright, so first I looked at the dataset and tried to understand what exactly we are predicting.

**The goal here is to predict whether a customer will make a repeat purchase within 30 days.**

So based on that:

- Label (Target Variable):
repeat_purchase_flag

  → This is clearly the output we want to predict because it tells us whether the customer actually made a repeat purchase or not.
- Data Leakage Column:
discount_used_on_repeat_order
  → This is a problem because this information is only available after the repeat purchase happens, so using it during training would give the model unfair future information.

**In simple words:**  
If we include this column, the model is basically “cheating” because it already knows something about the outcome.

# Task 2 — Missing Steps in ML Workflow

My manager directly jumped into training a gradient boosting model, but honestly, that’s skipping some really important steps.

## 1. Data Cleaning & Exploration (EDA)

Before building any model, I would first explore the dataset properly.

- Check for missing values
- Look for outliers (like extremely high order values)
- Understand distributions of features

**Why this matters:**  
If the data is messy or inconsistent, even the best model will give poor results.
“Garbage in = Garbage out.”

## 2. Train-Test Split

Another important step is splitting the data into training and testing sets.

**Why this matters:**

- The model should be evaluated on unseen data
- If we train and test on the same data, we get over-optimistic results

In real-world scenarios, we care about how well the model performs on new customers, not the ones it has already seen.

