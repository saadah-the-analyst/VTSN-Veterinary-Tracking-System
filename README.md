# VTSN – Veterinary Tracking System Nigeria
### Animal Disease Outbreak & Surveillance Tracker

**Veterinary Clinic Patient Record and Sickness Frequency Analyzer**

---

## Table of Contents

1. [Project Overview and Introduction](#1-project-overview-and-introduction)
2. [Why This Project Matters](#2-why-this-project-matters)
3. [Project Goals and Objectives](#3-project-goals-and-objectives)
4. [Team Members](#4-team-members)
5. [Technologies Used](#5-technologies-used)
6. [Recommended GitHub Folder Structure](#6-recommended-github-folder-structure)
7. [Step-by-Step Methodology](#7-step-by-step-methodology)
   - 7.1 Step 1 – Data Collection & Original Dataset Isolation
   - 7.2 Step 2 – Data Cleaning and Preprocessing (Pandas)
   - 7.3 Step 3 – Data Transformation and Structuring (Python Fundamentals)
   - 7.4 Step 4 – Statistical Analysis and Computation (NumPy)
   - 7.5 Step 5 – Data Visualization (Matplotlib)
   - 7.6 Step 6 – Result Interpretation and Review
   - 7.7 Step 7 – Final Documentation and Reporting
8. [Key Findings and Results Summary](#8-key-findings-and-results-summary)
9. [How Useful This Project Is to Veterinary Clinics](#9-how-useful-this-project-is-to-veterinary-clinics)
10. [Practical Recommendations for Veterinary Clinics](#10-practical-recommendations-for-veterinary-clinics)
11. [Future Recommendations and Next Steps](#11-future-recommendations-and-next-steps)
12. [How to Set Up and Run the Project](#12-how-to-set-up-and-run-the-project)
13. [Project Deliverables Checklist](#13-project-deliverables-checklist)
14. [Final Conclusion](#14-final-conclusion)

---

## 1. Project Overview and Introduction

This document is a complete and detailed guide for the **VTSN (Veterinary Tracking System Nigeria)** project. It is written in simple English so that anyone — students, lecturers, veterinary doctors, or GitHub visitors can easily understand what the project is about and how it works.

The full name of the project is: **Veterinary Clinic Patient Record and Sickness Frequency Analyzer**. It is also called **VTSN – Animal Disease Outbreak & Surveillance Tracker**.

The main idea of the project is very simple. Many veterinary clinics in Nigeria still keep animal patient records on paper. These paper files are often scattered, incomplete, or difficult to search. Because of this, animal doctors waste time looking for information and cannot easily see important patterns such as which diseases appear most often or which animals are at higher risk.

Our project solves this problem by creating a complete digital system using Python. The system takes raw clinic data, cleans it, organises it, calculates useful statistics, and produces clear charts. At the end, the clinic has a modern and reliable way to understand their patient records.

---

## 2. Why This Project Matters

Paper-based record keeping creates several real problems for veterinary clinics:

- It is hard to quickly find a particular patient’s history.
- It is difficult to know which sicknesses are most common.
- Doctors cannot easily see age or weight patterns of animals that visit the clinic.
- Risk levels of patients are not clearly recorded.
- Planning for medicines, staff, and equipment becomes guesswork.

By turning paper records into clean digital data and analysing them properly, this project helps clinics move from guesswork to informed decision-making. The system is built with tools that are free and widely available (Python, Pandas, NumPy, Matplotlib), so it can be used even by small clinics with limited resources.

---

## 3. Project Goals and Objectives

The main goals of this project are:

1. To collect and isolate a clean set of 1,000 authentic veterinary patient records.
2. To clean the data thoroughly so that missing values, duplicates, and text problems are removed.
3. To create useful new categories such as Age Group, Weight Class, Health Risk Level, and Symptom Severity.
4. To calculate important statistics about patient age and weight using NumPy.
5. To produce clear and professional charts that show the main patterns in the data.
6. To explain the results in simple language so that veterinary staff can use the findings.
7. To document the entire process so that other people can understand and continue the work.

---

## 4. Team Members

This project was built jointly by two team members:

- **Muhyideen Saadah Aduke**
- **Nnadiukwu Glory Vivian**

Both team members worked together on the data cleaning, transformation, statistical analysis, visualisation, and final documentation. The project was developed as a Python Data Analytics course project focused on the veterinary health and animal care sector.

---

## 5. Technologies Used

The project uses four main tools:

| Tool              | Purpose                                      |
|-------------------|----------------------------------------------|
| Python            | Core programming language                    |
| Pandas            | Data loading, cleaning and transformation    |
| NumPy             | Fast numerical calculations and statistics   |
| Matplotlib        | Creating professional charts and graphs      |
| Jupyter Notebook  | Interactive development and documentation    |

---

## 6. Recommended GitHub Folder Structure

When you upload this project to GitHub, we recommend the following clean folder structure:

```
VTSN-Veterinary-Tracking-System/
│
├── data/
│   ├── veterinary_clinical_data.csv
│   ├── authentic_veterinary_data.csv
│   ├── cleaned_authentic_veterinary_data.csv
│   ├── structured_authentic_veterinary_data.csv
│   └── step4_numpy_analyzed_data.csv
│
├── notebooks/
│   └── Vet_Clinic_Analysis_Project.ipynb
│
├── images/                          
│   ├── step1_data_collection.png
│   ├── step2_data_cleaning.png
│   ├── step3_data_transformation.png
│   ├── step4_numpy_analysis.png
│   └── step5_visualization.png
│
├── outputs/
│   └── veterinary_patient_visualizations_comprehensive.png
│
├── README.md
└── requirements.txt
```

---

## 7. Step-by-Step Methodology

The project follows a clear 7-step process. Each step is explained below.

### 7.1 Step 1 – Data Collection & Original Dataset Isolation

In the first step we started with the full raw dataset called `veterinary_clinical_data.csv`. This file contained **10,000 rows** and **10 columns** (AnimalName, Breed, Age, Weight_kg, MedicalHistory, and five symptom columns).

However, only the first 1,000 rows are **authentic** (real clinic records). The remaining 9,000 rows are **synthetic** (artificially generated data).

For this important reason, we deliberately extracted only the first 1,000 authentic rows using Python. We saved this clean and reliable subset as `authentic_veterinary_data.csv`. This authentic dataset became the official working data for all the remaining steps of the project.


**Result of Step 1:** A reliable file with exactly 1,000 rows and 10 columns ready for cleaning.

**Screenshot of Step 1 (Code):**

![Step 1 - Data Collection](images/step1_data_collection.png)

*(Replace the image above with your actual screenshot of the Step 1 code)*

---

### 7.2 Step 2 – Data Cleaning and Preprocessing (Pandas)

In Step 2 we loaded the authentic dataset and performed careful cleaning:

* **Missing Value Audit:** Performed comprehensive null-value scans (`df.isnull().sum()`), confirming **0 missing values** across all records.
* **Duplicate Elimination:** Scanned for identical record duplication (`df.duplicated().sum()`), verifying **0 duplicate rows** and ensuring statistical independence.
* **Text & String Standardization:** Standardized categorical text columns (`AnimalName`, `Breed`, `MedicalHistory`) by stripping invisible whitespace buffers and enforcing uniform title case formatting (e.g., converting lowercase `'cat'` to `'Cat'`).
* **Datatype Conversion:** Cast numerical features (`Age` and `Weight_kg`) into precise floating-point representations (`float64`) and generated descriptive statistical summaries to eliminate anomalous outliers.

After cleaning, the dataset was saved as `cleaned_authentic_veterinary_data.csv`. It still had 1,000 rows and 10 columns, but now it was clean and ready for transformation.

**Screenshot of Step 2 (Code):**

![Step 2 - Data Cleaning](images/step2_data_cleaning.png)

*(Replace the image above with your actual screenshot of the Step 2 code)*

---

### 7.3 Step 3 – Data Transformation and Structuring (Python Fundamentals)

This step used pure Python programming skills (functions, if-elif-else statements, and loops) to create new useful columns.

1. **Patient Age Demographics (`Age_Group`):**
   * *Young:* Patients $< 3$ years of age.
   * *Adult:* Patients between $3$ and $10$ years of age.
   * *Senior:* Patients $> 10$ years of age.
2. **Body Weight Classifications (`Weight_Class`):**
   * *Small Breed:* Animals weighing $< 10	ext{ kg}$.
   * *Medium Breed:* Animals weighing between $10	ext{ kg}$ and $25	ext{ kg}$.
   * *Large Breed:* Animals weighing $> 25	ext{ kg}$.
3. **Clinical Health Risk Stratification (`Health_Risk_Level`):**
   * *High Risk:* Flagged automatically for chronic conditions, history of renal impairment, or cardiac disorders.
   * *Low Risk:* Assigned to patients with verified, up-to-date vaccination records.
   * *Moderate Risk:* Applied to standard routine checkups, parasite treatments, or minor surgical histories.
4. **Symptom Processing & Iterative Looping:**
   * **Symptom Frequency Tallying:** Iterated through all five symptom tracking columns using dictionary mapping to aggregate and count distinct clinical occurrences (**801 unique symptom instances** cataloged).
   * **Critical Symptom Flagging (`Has_Fever_Flag`):** Executed conditional row scans to isolate fever presentations (`Yes` / `No`).
   * **Symptom Severity Load (`Symptom_Severity_Level`):** Categorized overall clinical burden based on symptom counts (*Mild*, *Moderate*, *Severe*).

After these transformations the dataset grew to **16 columns** and was saved as `structured_authentic_veterinary_data.csv`.

**Screenshot of Step 3 (Code):**

![Step 3 - Data Transformation](images/step3_data_transformation.png)

*(Replace the image above with your actual screenshot of the Step 3 code)*

---

### 7.4 Step 4 – Statistical Analysis and Computation (NumPy)

In this step we converted the Age and Weight columns into NumPy arrays so that calculations could be done very quickly.

**Key statistics calculated for Age:**
- Mean (average) age = **8.36 years**
- Median age = **8.20 years**
- Standard deviation = **4.70**
- Minimum age = **0.5 years**
- Maximum age = **18.0 years**
- 25th percentile = 4.7 years | 75th percentile = 12.0 years

**Key statistics calculated for Weight:**
- Mean weight = **14.99 kg**
- Median weight = **7.30 kg**
- Standard deviation = **12.55 kg**
- Minimum weight = **2.5 kg**
- Maximum weight = **45.0 kg**
- 25th percentile = 5.3 kg | 75th percentile = 26.0 kg

We also created NumPy-based weight tiers:
- Lightweight (under 5 kg) – 211 patients
- Standard (5–20 kg) – 459 patients
- Heavyweight (over 20 kg) – 330 patients

The final file from this step is `step4_numpy_analyzed_data.csv`.

**Screenshot of Step 4 (Code):**

![Step 4 - NumPy Analysis](images/step4_numpy_analysis.png)

*(Replace the image above with your actual screenshot of the Step 4 code)*

---

### 7.5 Step 5 – Data Visualization (Matplotlib)

We created a professional set of **7 charts** arranged in a clear multi-plot layout:

1. Patient Age Distribution (Histogram)
2. Patient Weight Distribution (Histogram)
3. Patient Breakdown by Weight Class (Bar Chart)
4. Patients by Health Risk Level (Bar Chart)
5. Patient Breakdown by Age Group (Bar Chart)
6. Top 5 Most Frequent Clinic Symptoms (Horizontal Bar Chart)
7. Top Patient Medical History Conditions (Horizontal Bar Chart)

All charts were saved together as one high-resolution image file named `veterinary_patient_visualizations_comprehensive.png` (300 DPI).

**Screenshot of Step 5 (Code):**

![Step 5 - Data Visualization](images/step5_visualization.png)

*(Replace the image above with your actual screenshot of the Step 5 code)*

---

### 7.6 Step 6 – Result Interpretation and Review

In this step we stepped back from the code and explained what the numbers and charts really mean for a veterinary clinic. The interpretation covers age patterns, weight patterns, risk levels, most common symptoms, and background medical histories. Full details are given in the “Key Findings” and “How Useful” sections below.

### 7.7 Step 7 – Final Documentation and Reporting

The last step was to gather every deliverable — clean data files, the Jupyter Notebook, the statistical results, the visual charts, and the written interpretation — into one complete and organised package ready for submission and for GitHub.

---

## 8. Key Findings and Results Summary

After analysing 1,000 authentic patient records, these are the main findings:

### Age Findings
- The average age of animals visiting the clinic is **8.36 years**.
- Adult and Senior animals make up the largest groups.
- Young animals (under 3 years) are fewer in number.

### Weight Findings
- The average weight is **14.99 kg**, but the median is only **7.30 kg**. This shows the data is right-skewed (many small animals and fewer heavy ones).
- Small and Medium breeds form the majority of daily visits.

### Health Risk Findings
- Most patients fall into the **Moderate Risk** category, which are (600) patients.
- High Risk patients are the next largest group, which are (236) patients.
- Low Risk patients are the smallest group, .

### Symptom Findings
- **Fever** and **Weight Loss** are the two most common clinical signs.
- Other frequent symptoms include Diarrhea, Coughing and Weakness.

### Medical History Findings
- Skin conditions history and recent surgery appear most often in the records.
- Many animals also have “No previous conditions” recorded.

---

## 9. How Useful This Project Is to Veterinary Clinics

This project is not just an academic exercise. It has real practical value for veterinary clinics in Nigeria and similar settings.

### Faster Access to Information
Instead of searching through piles of paper, clinic staff can open a clean digital table or look at a clear chart and immediately see patterns. This saves time during busy clinic hours.

### Better Understanding of Patient Population
Clinic managers can now know the typical age and weight of animals that visit. This helps them decide what sizes of cages, what strength of medicines, and what type of equipment to keep in stock.

### Improved Risk Awareness
By clearly labelling patients as High, Moderate or Low Risk, the clinic can give extra attention to animals that need it most. This improves the quality of care and reduces the chance of missing serious cases.

### Smarter Symptom Response
Knowing that Fever and Weight Loss are the top symptoms allows the clinic to prepare standard treatment protocols for these common problems. New staff can be trained more quickly.

### Support for Long-Term Planning
When a clinic understands its own data, it can plan better for the future — how many staff are needed, which medicines to order more of, and whether specialised services (for example senior animal care) should be expanded.

### Moving from Paper to Digital
The project shows a practical and low-cost way to start the journey from paper records to digital records. Even small clinics can begin with a similar Python-based approach.

---

## 10. Practical Recommendations for Veterinary Clinics

Based on the findings of this project, we make the following practical recommendations:

1. Start digitising the most recent patient records first. Even converting the last 6–12 months of paper files into a simple spreadsheet already brings big benefits.
2. Use clear categories (Age Group, Weight Class, Health Risk Level) when recording new patients. This makes future analysis much easier.
3. Pay special attention to animals that fall into the High Risk category and those presenting with Fever or Weight Loss.
4. Keep a regular stock of medicines and diagnostic materials that are commonly needed for the top symptoms identified in this study.
5. Train all clinical staff to record Medical History in a consistent way (for example always noting vaccination status, previous surgery, and chronic conditions).
6. Review the clinic’s own data at least once every three or six months so that new patterns can be spotted early.
7. Consider creating a simple digital dashboard (even using free tools) that shows the same charts produced in this project. This helps management and doctors see the situation at a glance.

---

## 11. Future Recommendations and Next Steps

This project is a solid foundation. There are many ways it can be improved and expanded in the future:

### Short-Term Improvements
- Collect more than 1,000 records so that the analysis becomes even more reliable.
- Add more details such as breed type, sex of the animal, vaccination dates, and treatment outcomes.

### Medium-Term Improvements
- Build a proper database (SQLite or PostgreSQL) instead of using only CSV files.
- Add automatic alerts when a High Risk patient or a patient with Fever is entered.
- Include simple prediction models (for example predicting which animals are more likely to develop certain conditions).

### Long-Term Vision
- Connect the system to mobile phones so that field veterinarians can enter data while visiting farms or homes.
- Link the system with national animal disease surveillance programmes so that early warning of outbreaks becomes possible.
- Expand the project into a full Veterinary Management System that also handles appointments, billing, and inventory.

These future steps would turn the current analysis tool into a complete digital support system for veterinary practice in Nigeria.

---

## 12. How to Set Up and Run the Project

Anyone who wants to run this project on their own computer can follow these simple steps:

1. Clone or download the GitHub repository.
2. Open a terminal (command prompt) and move into the project folder.
3. Install the required packages by running:  
   ```bash
   pip install -r requirements.txt
   ```
4. Open the Jupyter Notebook file that is inside the `notebooks` folder.
5. Run all the cells from top to bottom. The notebook will recreate the cleaned data, the statistics, and the charts.

**Required packages** (to be listed in `requirements.txt`):

```
pandas
numpy
matplotlib
jupyter
```

---

## 13. Project Deliverables Checklist

At the end of the project the following items have been successfully completed:

- [x] Authentic working dataset of 1,000 patient records
- [x] Fully cleaned dataset
- [x] Structured dataset with Age Group, Weight Class, Health Risk Level and Symptom Severity columns
- [x] NumPy statistical calculations for Age and Weight
- [x] Complete set of 7 professional charts saved as a high-resolution PNG file
- [x] Written interpretation of the results
- [x] Clear recommendations for veterinary clinics
- [x] Future development suggestions
- [x] Full documentation (this README and the Jupyter Notebook)

---

## 14. Final Conclusion

This project successfully shows how ordinary Python tools can solve a real problem faced by many veterinary clinics. By moving from scattered paper records to clean digital data, and by calculating statistics and drawing clear charts, we have created a practical system that helps animal doctors understand their patients better.

The work covers every important stage: data collection, cleaning, transformation, statistical analysis, visualisation, interpretation, and documentation. Everything has been written and organised so that other students, lecturers, or veterinary professionals can understand it and build upon it.

We hope this project encourages more clinics in Nigeria to start using simple data tools. Better records lead to better understanding, and better understanding leads to better care for animals.

Thank you for reading this complete documentation.

---

**Project created by:**  
Muhyideen Saadah Aduke  
Nnadiukwu Glory Vivian

**Industry Focus:** Veterinary Health and Animal Care  
**Project Type:** Python Data Analytics Course Project

---
