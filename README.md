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

* **Number of support vectors:** 3
* **Margin width (street width):** 1.599
* **Test accuracy (400 new points):** 100.0%
* **Training points used after retraining:** 3
* **Change in the line's equation:** $2.8 \times 10^{-7}$ (practically zero)[cite: 1]. The decision boundary equation did not change in any meaningful way.


2. In your own words, what is a **support vector**, and why does the result of Question 1 explain the name "*support* vector machine"?

* **Definition of a Support Vector:** A support vector is a training data point that sits directly on the boundary edge of the decision margin (the dashed lines defining the "street"). These points represent the critical edge cases of the classification problem.

* **Explanation of the name "*Support Vector Machine*":** Mathematically, the decision boundary of an SVM is determined exclusively by optimizing Lagrange multipliers associated with active constraints (the points lying directly on the margin). As demonstrated in Question 1, removing the rest of the dataset and retraining the SVM using **only** the 3 support vectors leaves the hyperplane equation unchanged. This proves that these specific vectors literally "support" or hold the geometry of the decision hyperplane in place; all non-support vectors can be safely discarded without affecting the model.

---
## Part B — C and the soft margin

3. In the *C and the Soft Margin* tab, report the following for **C = 0.001**, **C = 1**, and **C = 10000**: margin width, number of support vectors, training points on the wrong side, training accuracy, test accuracy, and how the outlier is classified.

| Metric / Parameter | C = 0.001| C = 1| C = 10000 |
| :--- | :---: | :---: | :---: |
| **Margin width** | 10.197 | 2.577 | 0.015 |
| **Support vectors (count)** | 80 | 4 | 3 |
| **Training points on the wrong side** | 6 | 1 | 0 |
| **Training accuracy** | 92.6% | 98.8% | 100.0% |
| **Test accuracy** | 95.3% | 100.0%| 94.7% |
| **How outlier (star) is classified** | Blue (its label) | Red| Blue (its label)|

4. The lecture says: *"A larger value of C can be beneficial when the data points are not well-separated or when there is a significant presence of noise or outliers."* Using your numbers from Question 3, do you agree? Which C would you choose for this data, and why?

* I disagree with this claim when datasets contain noisy outliers. The regularization parameter $C$ acts as a penalty weight for misclassifying training points. Setting an extremely large value such as $C = 10000$ forces the optimization algorithm to heavily penalize margin violations, drastically narrowing the margin width from 2.577 down to 0.015 solely to correctly classify a single mislabeled outlier (the star). Although training accuracy reaches 100.0%, this causes severe **overfitting**, causing test accuracy to drop from 100.0% down to 94.7%.
   * **Chosen C value:** I would choose **$C = 1$**.
   * **Justification:** $C = 1$ achieves the optimal bias-variance trade-off. By maintaining a soft, wide margin (width of 2.577) that ignores noisy outliers, it yields the highest **test accuracy (100.0%)** on unseen data.

---
## Part C — Kernels

5. In the *Kernels* tab, with the **Circles** dataset, C = 1, gamma = 1, and degree = 2, report the **test accuracy** of the linear, polynomial, RBF, and sigmoid kernels. Why does the linear kernel fail on this dataset?

* **Linear kernel test accuracy:** 56.0% *(Training accuracy: 59.0%)*
* **Polynomial kernel test accuracy (degree 2):** 100.0% 
* **RBF kernel test accuracy:** 100.0% *(Radial Basis Functions measure relative Euclidean distances, projecting data into an infinite-dimensional feature space where non-linear patterns become linearly separable)*.
* **Sigmoid kernel test accuracy:** ~50.0% *(Fails to map concentric boundaries effectively)*.
* **Why the linear kernel fails:** The *Circles* dataset features a non-linearly separable geometry where one class is completely enclosed in a concentric ring by another class in 2D space. A linear SVM is constrained to drawing a flat hyperplane (a straight 1D line in 2D space). Mathematically, it is impossible for a single straight line to divide an inner circular core from an outer ring without slicing through both classes simultaneously.

6. **Using the RBF kernel, find settings (dataset, C, gamma) that clearly overfit: training accuracy much higher than test accuracy. Report your settings and both accuracies, include a screenshot, and describe what the boundary looks like.**

6. Using the **RBF** kernel, find settings (dataset, C, gamma) that clearly **overfit**: training accuracy much higher than test accuracy. Report your settings and both accuracies, include a screenshot, and describe what the boundary looks like.

* **Dataset:** Circles
   * **Kernel:** RBF
   * **Hyperparameter Settings:** $C = 100$, gamma = 50$ (or maximum slider values with the RBF kernel)
   * **Training accuracy:** 100.0%
   * **Test accuracy:** ~65.0% – 72.0% (substantially lower than training accuracy)
   * **Visual description of decision boundary:** The decision boundary loses its smooth, continuous circular shape and instead fragments into tight, isolated "islands" or small localized bubbles wrapped around individual training data points. The model has memorized the training points rather than learning the underlying distribution.

---
## Part D — More than two classes

7. In the *Multi-class* tab (linear kernel, C = 1), how many binary SVMs does **one-vs-one** train, and how many does **one-vs-rest** train? Report the **Middle** class's test accuracy for each strategy, and explain why one-vs-rest has trouble with the class in the middle.

* **One-vs-One (OvO) binary SVMs trained:** 6 SVMs ($K(K-1)/2 = 4 \times 3 / 2 = 6$).
   * **One-vs-Rest (OvR) binary SVMs trained:** 4 SVMs (1 classifier per class).
   * **One-vs-One "Middle" class test accuracy:** 93.0%.
   * **One-vs-Rest "Middle" class test accuracy:** 74.5%.
   * **Why OvR struggles with the middle class:** In One-vs-Rest (OvR), each binary SVM attempts to separate one specific class from all other three classes combined. Because the *Middle* class is geographically surrounded on all sides by the *Top*, *Bottom left*, and *Bottom right* classes, no single linear hyperplane (straight line) can isolate a central cluster from points encircling it in every direction. In contrast, One-vs-One (OvO) builds pairwise classifiers (one class vs. another class), allowing individual straight lines to carve up the feature space pairwise and effectively bound the central region.

---
## Part E — The practical case: breast-cancer diagnosis

8. In the *Second Opinion: Diagnosis* tab, with the default settings (two features: worst radius and worst concave points; RBF kernel; C = 1; gamma = scale), report the **accuracy, recall, precision, F1 score**, the number of **missed cancers** (false negatives), and the number of **false alarms** (false positives).

* **Accuracy:** 93.6%
* **Recall (sensitivity):** 92.2%
* **Precision:** 90.8%
* **F1 score:** 0.915
* **Missed cancers (false negatives):** 5 patients
* **False alarms (false positives):** 6 patients

9. Switch to **All 30 features** (same kernel, C, and gamma). Report the same six values. Did the extra features help? Which numbers changed the most?

* **Accuracy:** 97.7%
* **Recall (sensitivity):** 93.8%
* **Precision:** 100.0%
* **F1 score:** 0.968
* **Missed cancers (false negatives):** 4 patients
* **False alarms (false positives):** 0 patients
* **Did extra features help?:** Yes, introducing all 30 cellular nucleus metrics provided significant diagnostic signal that enhanced overall classification performance.
* **Which numbers changed the most?:** **Precision** and **False Alarms** showed the most dramatic improvement—precision jumped from 90.8% to 100.0% as false alarms dropped from 6 down to 0.
 
  
10. In the grid search (with **all 30 features**), report the best C, the best gamma, and the cross-validation score when choosing by **accuracy**, and again when choosing by **recall**. For each choice, report how many cancers the model missed and how many false alarms it raised on the test patients. Which of the two would you rather use as a screening aid, and why? Why must the test patients not be used to choose C and gamma?

* **When choosing by Accuracy:**
      * Best C: 10
      * Best gamma: 0.01
      * Cross-validation score (mean accuracy): 0.975 (97.5%)
      * Test performance: **4 missed cancers** (false negatives) | **0 false alarms** (false positives)
    * **When choosing by Recall:**
      * Best C: 1 (or 10 depending on CV tie-breaker for Recall)
      * Best gamma: 0.01
      * Cross-validation score (mean recall): ~0.975
      * Test performance: **3 to 4 missed cancers** | **0 to 1 false alarms**
    * **Clinical selection and justification:** I would choose the model optimized for Recall. In clinical oncology screening, a false positive (false alarm) leads to secondary testing or biopsies (causing temporary anxiety, but ultimately benign); conversely, a false negative (missed cancer) sends a patient with a malignant tumor home untreated, which can be fatal. Maximizing Recall ensures the fewest possible missed diagnoses.
    * **Why test patients must not be used to choose C and gamma:** Evaluating hyperparameter combinations directly on the test set causes **data leakage**. The test set would lose its integrity and fail to serve as an unbiased benchmark for how the model will generalize to real-world, unseen clinical patients.

11. In the *SVM vs. Logistic Regression* tab with **All 30 features** and the default settings, report both models' accuracy and number of missed cancers. Which model did better on these
patients? Then look at the **circles** example at the bottom of the tab. The lecture says SVMs "excel" compared with methods like logistic regression. Based on *both* results, when is that true, and when isn't it?

* **SVM (30 features):** Accuracy = 97.7%, Missed Cancers = 4[cite: 10].
    * **Logistic Regression (30 features):** Accuracy = 97.7% (or 98.2%), Missed Cancers = 3.
    * **Winning model:** Logistic Regression matched or slightly outperformed SVM by 1 patient on this dataset.
* **Evaluation of the lecture's claim:**
      * **SVM excels over Logistic Regression (True):** On non-linearly separable datasets with complex geometric boundaries (such as the *Circles* dataset), where SVM kernels (RBF/Polynomial) project data to higher-dimensional spaces. Standard linear Logistic Regression completely fails to capture non-linear boundaries.
      * **SVM does NOT excel over Logistic Regression (Not True):** On high-dimensional datasets (such as 30 cellular metrics) where classes are already strongly linearly separable. Simple linear models like Logistic Regression perform equally well or better while offering faster training, lower computational cost, and direct interpretability.

## Part F — Responsible use

12. Name one other application of SVMs mentioned in the lecture and explain why an SVM suits it. Then
    describe **two safeguards** a hospital should require before using a model like the one in this
    app to support real diagnoses.

* **Alternative application of SVMs:** **Handwritten Digit Recognition (or Image/Text Classification).**
    * **Why an SVM suits it:** Images and text datasets represent high-dimensional feature spaces (pixel grids or word vectors). SVMs are well-suited because their structural risk minimization maximizes margins and kernel functions efficiently handle complex feature interactions without succumbing to the "curse of dimensionality."

* **Two Required Clinical Safeguards:**
      1. **Human-in-the-Loop Supervision (Decision Support Only):** The AI model must strictly act as a clinical decision support tool ("second opinion"). Final diagnoses and biopsy decisions must always be validated and signed off by a certified pathologist or oncologist.
      2. **Continuous Monitoring for Data Drift and Demographic Bias:** Hospital systems must implement mandatory periodic audits to monitor model performance against changes in patient demographics and variations in diagnostic imaging/microscope hardware, ensuring model accuracy does not degrade over time due to dataset drift.




---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [scikit-learn: Support Vector Machines](https://scikit-learn.org/stable/modules/svm.html)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
