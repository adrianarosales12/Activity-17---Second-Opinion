# Activity 17: Second Opinion — Support Vector Machines for Breast-Cancer Diagnosis
## Session 31
## Due date (mm/dd/yyyy): 11/08/2026
## Adriana Rosales González
## Delivery Format: [] Video URL | [X] Markdown file | [] Jupyter Notebook file

---

# Activity Description

## The Story

When a breast mass is found, a doctor can take a tiny sample of cells with a fine needle and
examine it under a microscope. In the early 1990s, researchers at the University of Wisconsin
measured 30 properties of the cell nuclei in those images (size, shape, texture...) for 569
patients whose diagnosis was later confirmed. Can a computer learn to tell **malignant** (cancer)
from **benign** masses from those measurements, as a "second opinion" for the doctor?

You will answer that with a **Support Vector Machine (SVM)**. First you will see exactly how an SVM
works on small 2D examples: the "widest street", support vectors, the **C** parameter, and
**kernels**. Then you will apply it to the real medical data and decide how you would tune it and
whether you would trust it.

---
### Your Tasks

1. **In The Widest Street**, read the explanation, then switch on **"Retrain the SVM using only the
   support vectors"**. Take a screenshot with the switch on.

<img width="623" height="569" alt="image" src="https://github.com/user-attachments/assets/24b4faf4-53d4-4002-b53d-4d2a700c7fe0" />

   
---
2. **In C and the Soft Margin**, set C to **0.001**, then **1**, then **10000**, and take a
   screenshot of each. Also look at the "Every C at once" chart.

-** C = 0.001**

<img width="582" height="638" alt="image" src="https://github.com/user-attachments/assets/536349b4-cba0-42fa-947d-e7ed2cd6f4a9" />

    
 - **C = 1**

<img width="572" height="643" alt="image" src="https://github.com/user-attachments/assets/580f79dd-b4d2-4fb4-b985-b44f596a7618" />

  
- **C = 10,000**

   <img width="568" height="638" alt="image" src="https://github.com/user-attachments/assets/09180103-94ba-4e29-9f1b-5fd216d62d36" />

---
3. **In Kernels**, with the Circles dataset, C = 1, gamma = 1, and degree = 2, try all four kernels.
   Then use the RBF kernel and raise gamma (and C) until the boundary overfits. Take a screenshot of
   the overfitting case.
<img width="584" height="479" alt="image" src="https://github.com/user-attachments/assets/c09257e5-94cf-49aa-af5b-ed25af5d4e68" />

 - **TESTS**

  <img width="560" height="451" alt="image" src="https://github.com/user-attachments/assets/1b35b155-933e-4a8d-ab3c-d566555a846b" />
<img width="586" height="479" alt="image" src="https://github.com/user-attachments/assets/4a21911c-30e8-416d-98db-178e33d085f7" />

   
---
4. **In Multi-class**, keep the linear kernel and C = 1. Take a screenshot showing all three charts
   and the table.

<img width="556" height="519" alt="image" src="https://github.com/user-attachments/assets/16828505-6141-4bbe-95bb-2e51030b7df6" />


---
5. **In Second Opinion: Diagnosis**, read the results with the default settings, then switch to
   **All 30 features**. Take a screenshot of each, including the confusion matrix.

<img width="1232" height="564" alt="image" src="https://github.com/user-attachments/assets/fdaac738-3e6a-4bf8-a5ed-7cba88bdb0f0" />

<img width="1210" height="348" alt="image" src="https://github.com/user-attachments/assets/9439f5c9-9290-4c8f-a482-0e202f36ffaf" />

   
---
6. **Still in the Diagnosis tab (all 30 features)**, scroll to the grid search. Choose by
   **Accuracy**, then by **Recall**, and take a screenshot of each heatmap and its test results.

  <img width="1231" height="550" alt="image" src="https://github.com/user-attachments/assets/992e4840-909d-4061-bf58-ee6592d855e7" />

<img width="1203" height="535" alt="image" src="https://github.com/user-attachments/assets/55ca4c73-a3fb-4049-a8e1-771c7879b075" />

<img width="1229" height="563" alt="image" src="https://github.com/user-attachments/assets/69dc06d3-56c3-42dc-8f9c-eea9af63e3af" />

   
---
7. **In SVM vs. Logistic Regression**, look at both the two-feature and the 30-feature comparisons,
   and the circles example at the bottom. Take a screenshot of the 30-feature table.

<img width="569" height="643" alt="image" src="https://github.com/user-attachments/assets/6dbfa169-d0a8-44dc-9c37-10effc15a32f" />

 <img width="578" height="428" alt="image" src="https://github.com/user-attachments/assets/6ee2a716-bab7-4c2f-a8dc-1b362c6e4ce8" />
 
   
---
8. **Fill out `A17_ReflectionQuestions.md`**, using the exact numbers from your screenshots, and
   submit it along with your labeled screenshots (a `.zip` with the `.md` file and the images is
   fine).

# Activity 17 — Reflection Questions: Second Opinion (Support Vector Machines)

Answer every question using the app's **default settings**, unless a question tells you to change
something. Submit this file together with your labeled screenshots — do not just describe the app,
use your actual results.


## Part A — The widest street (margin and support vectors)

1. In *The Widest Street* tab, report the number of **support vectors**, the **margin width**, and the **test accuracy**. Then turn on **"Retrain the SVM using only the support vectors"**: how many training points were used, and how much did the line change?

* **Number of support vectors:** 3[cite: 1]
* **Margin width (street width):** 1.599[cite: 1]
* **Test accuracy (400 new points):** 100.0%[cite: 1]
* **Training points used after retraining:** 3[cite: 1]
* **Change in the line's equation:** $2.8 \times 10^{-7}$ (practically zero)[cite: 1]. The decision boundary equation did not change in any meaningful way[cite: 1].


2. In your own words, what is a **support vector**, and why does the result of Question 1 explain the name "*support* vector machine"?

* **Definition of a Support Vector:** A support vector is a training data point that sits directly on the boundary edge of the decision margin (the dashed lines defining the "street". These points represent the critical edge cases of the classification problem.
* **Explanation of the name "*Support Vector Machine*":** Mathematically, the decision boundary of an SVM is determined exclusively by optimizing Lagrange multipliers associated with active constraints (the points lying directly on the margin). As demonstrated in Question 1, removing the rest of the dataset and retraining the SVM using **only** the 3 support vectors leaves the hyperplane equation unchanged (an imperceptible variation of $2.8 \times 10^{-7}$)[cite: 1]. This proves that these specific vectors literally "support" or hold the geometry of the decision hyperplane in place; all non-support vectors can be safely discarded without affecting the model[cite: 1].
---
## Part B — C and the soft margin

3. In the *C and the Soft Margin* tab, report the following for **C = 0.001**, **C = 1**, and **C = 10000**: margin width, number of support vectors, training points on the wrong side, training accuracy, test accuracy, and how the outlier is classified.

4. The lecture says: *"A larger value of C can be beneficial when the data points are not well-separated or when there is a significant presence of noise or outliers."* Using your numbers from Question 3, do you agree? Which C would you choose for this data, and why?

---
## Part C — Kernels

5. In the *Kernels* tab, with the **Circles** dataset, C = 1, gamma = 1, and degree = 2, report the **test accuracy** of the linear, polynomial, RBF, and sigmoid kernels. Why does the linear kernel fail on this dataset?

6. Using the **RBF** kernel, find settings (dataset, C, gamma) that clearly **overfit**: training accuracy much higher than test accuracy. Report your settings and both accuracies, include a screenshot, and describe what the boundary looks like.

---
## Part D — More than two classes

7. In the *Multi-class* tab (linear kernel, C = 1), how many binary SVMs does **one-vs-one** train, and how many does **one-vs-rest** train? Report the **Middle** class's test accuracy for each strategy, and explain why one-vs-rest has trouble with the class in the middle.

---
## Part E — The practical case: breast-cancer diagnosis

8. In the *Second Opinion: Diagnosis* tab, with the default settings (two features: worst radius and worst concave points; RBF kernel; C = 1; gamma = scale), report the **accuracy, recall, precision, F1 score**, the number of **missed cancers** (false negatives), and the number of **false alarms** (false positives).

9. Switch to **All 30 features** (same kernel, C, and gamma). Report the same six values. Did the extra features help? Which numbers changed the most?

10. In the grid search (with **all 30 features**), report the best C, the best gamma, and the cross-validation score when choosing by **accuracy**, and again when choosing by **recall**. For each choice, report how many cancers the model missed and how many false alarms it raised on the test patients. Which of the two would you rather use as a screening aid, and why? Why must the test patients not be used to choose C and gamma?

11. In the *SVM vs. Logistic Regression* tab with **All 30 features** and the default settings, report both models' accuracy and number of missed cancers. Which model did better on these
patients? Then look at the **circles** example at the bottom of the tab. The lecture says SVMs "excel" compared with methods like logistic regression. Based on *both* results, when is that true, and when isn't it?

## Part F — Responsible use

12. Name one other application of SVMs mentioned in the lecture and explain why an SVM suits it. Then
    describe **two safeguards** a hospital should require before using a model like the one in this
    app to support real diagnoses.






---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [scikit-learn: Support Vector Machines](https://scikit-learn.org/stable/modules/svm.html)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
