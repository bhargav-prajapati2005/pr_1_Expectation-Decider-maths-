# 📊 Expectation Decider

### Mathematics & Advanced Statistics | Probability Analysis Project

> **Expectation Decider** is a probability and statistics-based data analysis project designed to analyze patterns related to student exam performance.

---

## 📌 Project Overview

The **Expectation Decider** project analyzes a dataset of **200 students** containing information about:

* Study hours per week
* Lecture attendance percentage
* Group discussion participation
* Previous test score
* Final exam result

The objective is to apply **Probability and Statistical concepts** to understand patterns associated with students passing a competitive mathematics examination.

---

## 🎯 Project Objective

The main objectives of this project are to:

1. Understand basic probability concepts.
2. Calculate empirical and theoretical probabilities.
3. Create and analyze a random variable and probability distribution.
4. Calculate mean and variance.
5. Visualize probability events using a Venn-style analysis.
6. Create a contingency table.
7. Calculate joint, marginal, and conditional probabilities.
8. Understand independent, dependent, and mutually exclusive events.
9. Apply Bayes' Theorem.
10. Summarize factors associated with the probability of passing.

---

## 📂 Dataset Description

The dataset contains **200 student records**.

| Column                | Description                                   |
| --------------------- | --------------------------------------------- |
| `study_hours`         | Number of hours a student studied per week    |
| `attendance`          | Percentage attendance in lectures             |
| `group_discussion`    | Participation in group discussions (`Yes/No`) |
| `previous_test_score` | Previous internal test marks out of 100       |
| `final_exam_pass`     | Final competitive exam result (`Pass/Fail`)   |

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **NumPy**
* **Matplotlib**
* Probability
* Statistics
* Data Analysis

---

## 📁 Project Structure

```text
Expectation-Decider/
│
├── README.md
│
├── Expectation_Decider_Python.ipynb
│
├── expectation_decider_dataset.csv
│
└── PR1_Expectation_Decider.pdf
```

---

# 📚 Analysis Tasks

## 1. Understanding Probability

The project explains:

### What is Probability?

Probability represents the chance or likelihood of an event occurring.

### Dataset Examples

Examples of probability events include:

* A randomly selected student passes the exam.
* A student studies more than 10 hours per week.
* A student participates in group discussion.

The corresponding probabilities are calculated using Python.

---

# 2. Empirical & Theoretical Probability

### Empirical Probability

Empirical probability is calculated using observed data.

For example:

```text
P(Pass) =
Number of students who passed
--------------------------------
Total number of students
```

Python implementation:

```python
empirical_probability = (
    df['final_exam_pass'] == 'Pass'
).mean()

print(empirical_probability)
```

### Theoretical Probability

For three independent selections, the number of passes can be modeled using the **Binomial Distribution**.

Formula:

```text
P(X = k) = C(n,k) × p^k × (1-p)^(n-k)
```

---

# 3. Random Variable & Probability Distribution

Let:

```text
X = Number of students passing among 3 randomly selected students
```

Therefore:

```text
X = 0, 1, 2, 3
```

The probability distribution is calculated using the binomial model.

### Mean

```text
Mean = n × p
```

### Variance

```text
Variance = n × p × (1-p)
```

Python:

```python
mean_x = 3 * p
variance_x = 3 * p * (1-p)

print("Mean =", mean_x)
print("Variance =", variance_x)
```

---

# 4. Venn Diagram Analysis

Two events are analyzed:

### Event A

Students who study more than **10 hours per week**.

```python
A = df['study_hours'] > 10
```

### Event B

Students who have attendance greater than **80%**.

```python
B = df['attendance'] > 80
```

### Intersection

Students satisfying both conditions:

```python
A & B
```

The project calculates:

* A only
* B only
* A ∩ B
* Neither

A chart is also generated to visualize these groups.

---

# 5. Contingency Table

A contingency table is created between:

```text
group_discussion
        vs.
final_exam_pass
```

Python:

```python
table = pd.crosstab(
    df['group_discussion'],
    df['final_exam_pass']
)

print(table)
```

The table is used to calculate:

### Joint Probability

```text
P(Group Discussion = Yes AND Pass)
```

### Marginal Probability

```text
P(Pass)
```

### Conditional Probability

```text
P(Pass | Group Discussion = Yes)
```

Python:

```python
joint_probability = (
    (df['group_discussion'] == 'Yes') &
    (df['final_exam_pass'] == 'Pass')
).mean()
```

---

# 6. Understanding Relationships

Conditional probability helps answer questions such as:

> What is the probability that a student passes when the student participates in group discussion?

Formula:

```text
P(A|B) = P(A ∩ B) / P(B)
```

The project compares:

```text
P(Pass | Group Discussion = Yes)
```

with:

```text
P(Pass)
```

If these probabilities differ, the events are not independent under the comparison used in the analysis.

### Mutually Exclusive Events

Group discussion participation and passing cannot be mutually exclusive because a student can participate in group discussion **and** pass the exam.

---

# 7. Bayes' Theorem

The project provides the following historical information:

```text
P(High Attendance | Pass) = 70%

P(High Attendance | Fail) = 40%

P(High Attendance) = 60%
```

Bayes' Theorem:

```text
P(Pass | High Attendance)
=
P(High Attendance | Pass) × P(Pass)
-----------------------------------
P(High Attendance)
```

The notebook uses the pass probability estimated from the dataset for the `P(Pass)` term.

Python:

```python
p_high_given_pass = 0.70
p_high_given_fail = 0.40
p_high = 0.60

p_pass_dataset = (
    df['final_exam_pass'] == 'Pass'
).mean()

bayes_result = (
    p_high_given_pass * p_pass_dataset
) / p_high

print(
    "P(Pass | High attendance) =",
    bayes_result
)
```

---

# 📊 Key Statistical Concepts Used

This project demonstrates the following concepts:

* Probability
* Empirical Probability
* Theoretical Probability
* Random Variable
* Probability Distribution
* Mean
* Variance
* Venn Diagram
* Joint Probability
* Marginal Probability
* Conditional Probability
* Independent Events
* Mutually Exclusive Events
* Contingency Table
* Bayes' Theorem
* Binomial Distribution

---

# 💻 How to Run the Project

## Step 1 — Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

## Step 2 — Open the Project

Open the project folder in:

* Jupyter Notebook
* JupyterLab
* VS Code
* Google Colab

## Step 3 — Open the Notebook

Open:

```text
Expectation_Decider_Python.ipynb
```

## Step 4 — Keep the Dataset in the Same Folder

Make sure:

```text
expectation_decider_dataset.csv
```

is available in the same working directory.

## Step 5 — Run the Notebook

Run the cells sequentially from top to bottom.

---

# 📦 Python Libraries

Install the required libraries using:

```bash
pip install pandas numpy matplotlib
```

---

# 📈 Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Probability Analysis
   ↓
Empirical Probability
   ↓
Theoretical Probability
   ↓
Random Variable
   ↓
Probability Distribution
   ↓
Mean & Variance
   ↓
Venn Analysis
   ↓
Contingency Table
   ↓
Conditional Probability
   ↓
Independence Analysis
   ↓
Bayes' Theorem
   ↓
Final Insights
```

---

# 🔍 Project Insights

The analysis examines how the following variables relate to the exam outcome:

### 📖 Study Hours

Students' weekly study hours are analyzed as one of the probability events.

### 🏫 Attendance

Attendance above **80%** is used as a high-attendance event.

### 👥 Group Discussion

Participation is compared with final exam outcomes using a contingency table and conditional probability.

### 📝 Previous Test Score

Previous internal test performance is included in the dataset as an additional student-performance variable.

> **Note:** The generated dataset is intended for project/practical analysis. Its results should not be interpreted as real-world evidence about actual students.

---

# 📋 Assignment Coverage

| Requirement              | Status      |
| ------------------------ | ----------- |
| Probability basics       | ✅ Completed |
| Probability terminology  | ✅ Covered   |
| Probability examples     | ✅ Completed |
| Empirical probability    | ✅ Completed |
| Theoretical probability  | ✅ Completed |
| Random variable          | ✅ Completed |
| Probability distribution | ✅ Completed |
| Mean                     | ✅ Completed |
| Variance                 | ✅ Completed |
| Venn analysis            | ✅ Completed |
| Contingency table        | ✅ Completed |
| Joint probability        | ✅ Completed |
| Marginal probability     | ✅ Completed |
| Conditional probability  | ✅ Completed |
| Relationship analysis    | ✅ Completed |
| Bayes' Theorem           | ✅ Completed |
| Python implementation    | ✅ Completed |
| Jupyter Notebook         | ✅ Included  |

---

# 🎥 Project Explanation Video

**Video Link:**
`Add your Google Drive / YouTube Unlisted link here`

The assignment requires a video showing the face through webcam picture-in-picture and the complete desktop screen while explaining the tasks. The specified duration is **5–10 minutes**.

---

# 📂 Repository Contents

This repository should contain:

```text
📁 Expectation-Decider
│
├── 📄 README.md
├── 📓 Expectation_Decider_Python.ipynb
├── 📊 expectation_decider_dataset.csv
└── 📄 Calculation(img).pdf
```

The project brief specifies that the GitHub repository should contain the PDF, dataset if applicable, notebook, and README.

---

# 👨‍💻 Author

**Bhargav Prajapati**

### Skills Demonstrated

* Python
* Data Analysis
* Probability & Statistics
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook
* GitHub

---

