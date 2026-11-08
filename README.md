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

**  - C = 0.001**

<img width="582" height="638" alt="image" src="https://github.com/user-attachments/assets/536349b4-cba0-42fa-947d-e7ed2cd6f4a9" />

    
**  - C = 1**

<img width="572" height="643" alt="image" src="https://github.com/user-attachments/assets/580f79dd-b4d2-4fb4-b985-b44f596a7618" />

  
**  - C = 10,000**

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

   > 💡 **Hint:** Look at the blue *Middle* class. Can a single straight line separate it from all
   > three other classes at once?

5. **In Second Opinion: Diagnosis**, read the results with the default settings, then switch to
   **All 30 features**. Take a screenshot of each, including the confusion matrix.

   > 💡 **Hint:** In medicine, the two kinds of mistakes are not equally bad. The confusion matrix
   > spells them out: *missed cancers* and *false alarms*.

6. **Still in the Diagnosis tab (all 30 features)**, scroll to the grid search. Choose by
   **Accuracy**, then by **Recall**, and take a screenshot of each heatmap and its test results.

   > 💡 **Hint:** The heatmap is computed only from the training patients. The test patients are used
   > once, at the end, for the winning combination.

7. **In SVM vs. Logistic Regression**, look at both the two-feature and the 30-feature comparisons,
   and the circles example at the bottom. Take a screenshot of the 30-feature table.

   > 💡 **Hint:** Read the blue message under the table: it says which model won on these patients,
   > and by how many patients.

8. **Fill out `A17_ReflectionQuestions.md`**, using the exact numbers from your screenshots, and
   submit it along with your labeled screenshots (a `.zip` with the `.md` file and the images is
   fine).

   > 💡 **Hint:** Before submitting, check each answer against **How Your Grade Is Calculated**
   > below. It lists exactly what earns full points on every question.

### How Your Grade Is Calculated

Your grade is out of **100 points**, split across the 12 reflection questions. There are three
kinds of questions, and each kind is graded differently:

- **Exact answers** (Q1, Q3, Q5, Q8, Q9, and the numbers in Q7, Q10, Q11): there is one correct
  value, read from the app. With the settings the question gives, everyone sees exactly the same
  numbers. You get full points for correct values and partial credit when some parts are right.
  Small rounding differences are accepted.
- **Your own experiment** (Q6): every student's settings are different, so there is no single right
  number. But the app always gives exactly the same result for the same settings, so any setting you
  report can be re-run and checked. Numbers that no setting can reproduce get no credit.
- **Explain in your own words** (Q2, Q4, Q12, and the explanations in Q5, Q7, Q9, Q10, Q11): graded
  on four levels.
  - **Excellent:** complete, correct, and supported by your own numbers.
  - **Proficient:** correct, but missing a required part or not tied to your own numbers.
  - **Developing:** vague, incomplete, or partly wrong.
  - **Insufficient:** missing or wrong.

---






---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [scikit-learn: Support Vector Machines](https://scikit-learn.org/stable/modules/svm.html)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
