# 📊 Medical Appointment No-Show Risk Analytics Dashboard

## Project Overview

This project analyzes medical appointment no-show behavior using a structured risk modeling framework.

The objective is to identify and quantify:

- Structural risk drivers  
- Behavioral persistence patterns  
- Intervention effectiveness (SMS reminders)  
- Interaction effects between risk factors  

The dashboard was developed in **Power BI**, with feature engineering performed in **Power Query** and analytical measures built using **DAX**.

---

## 📁 Data Engineering & Feature Construction

### 🔹 Raw Dataset

The original dataset used for this analysis is publicly available on Kaggle:

👉 **Download Raw Dataset:**  
[Kaggle Dataset Link](https://www.kaggle.com/datasets/joniarroba/noshowappointments)

The raw dataset contains transactional appointment records without behavioral sequencing or engineered risk features.

Key original fields include:

- Patient ID  
- Appointment Date  
- Scheduled Date  
- SMS Received  
- No-Show Flag  
- Clinical indicators  

---

## 🔧 Transformation Approach (Power Query)

Significant feature engineering was performed to enable longitudinal and risk-based analysis.

### 1️⃣ Patient-Level Temporal Reconstruction

Appointments were grouped by **Patient ID** and sorted chronologically to:

- Generate appointment sequence index  
- Derive previous appointment date (lag variable)  
- Derive previous no-show flag  
- Calculate days between visits  
- Classify behavioral state:
  - `First Appointment`
  - `After Show`
  - `After No-Show`

This enabled behavioral persistence modeling rather than simple row-level aggregation.

---

### 2️⃣ Structural Feature Engineering

Additional engineered features include:

- Lead Time (Scheduled Date → Appointment Date)  
- Lead Time Buckets (`Same Day`, `1–2`, `3–4`, `5–6`, `7+`)  
- Long vs Short Lead Classification  
- Repeat Patient Indicator  
- Age Buckets  
- Normalized SMS Flag  

---

## 🧾 Engineered Analytical Dataset

The transformed dataset used for dashboard modeling is available here:

👉 **Download Engineered Dataset:**  
[Engineered Dataset Link Here](/Medical_Appointments_No_Show_May_2016.xlsx)

This dataset includes:

- Appointment sequence index  
- Previous no-show flag  
- Days between visits  
- Behavioral state classification  
- Lead time buckets  
- Long/Short lead flags  
- Analytical segmentation fields  

This engineered dataset serves as the analytical foundation for all modeling performed in the dashboard.

---

## 📊 Analytical Framework

The dashboard is organized into four analytical layers:

---

### 1️⃣ Overview

System-level exposure and primary risk drivers.

Includes:

- Total Appointments  
- No-Show Appointments  
- No-Show Rate  
- SMS Effect Delta  
- No-Show Contribution by Driver Type  
- Relative Risk across key segments  

This page establishes the scale of the problem and identifies amplification drivers.

---

### 2️⃣ Behavioral Analysis

Evaluates whether prior attendance behavior predicts future no-show risk.

Includes:

- No-Show Rate by Behavioral State  
- Relative Risk by Behavioral State  
- Behavioral State × Lead Time Interaction  

This section quantifies behavioral persistence and recurrence probability.

---

### 3️⃣ Structural Analysis

Examines booking horizon as a structural driver.

Includes:

- Lead Time Distribution  
- No-Show Rate by Lead Time Buckets  
- Short vs Long Lead Comparison  
- Long Lead Relative Risk  

This section demonstrates how extended booking horizons materially increase no-show likelihood.

---

### 4️⃣ Intervention Analysis

Assesses SMS reminder effectiveness and operational reach.

Includes:

- No-Show Rate by SMS Status  
- Relative Risk by SMS Status  
- SMS × Lead Time Interaction  
- Reminder Coverage  
- SMS Effect Delta  

This section separates risk intensity from mitigation impact and highlights optimization opportunities.

---

## 📈 Core Metrics

### No-Show Rate
No-Show Appointments / Total Appointments

### Relative Risk Index
Segment No-Show Rate / Overall No-Show Rate
used to quantify risk amplification or suppression relative to baseline.

### Contribution Percentage
Segment No-Show Volume / Total No-Show Volume
Separates risk intensity from volume impact.

### SMS Effect Delta  
Difference in no-show rate between SMS exposure groups.

---


## 🖼 Dashboard Screenshots



### Overview Page
![Overview Screenshot](/Screenshots/Overview.PNG)

### Behavioral Analysis
![Behavioral Screenshot](/Screenshots/Behavior.PNG)

### Structural Analysis
![Structural Screenshot](Screenshots/Structural.png)

### Intervention Analysis
![Intervention Screenshot](Screenshots/Intervention.png)

---

## 🛠 Technical Stack

- Power BI  
- Power Query (M Language)  
- DAX

---

## Power BI Report Access

* [Click to download Power BI file](/Power%20BI%20Representation.pbix)

---

## 🎯 Project Highlights

This project demonstrates:

- Longitudinal feature engineering in Power Query  
- Lag variable construction within grouped data  
- Behavioral state reconstruction  
- Relative risk modeling  
- Interaction effect analysis  
- Executive-focused analytical storytelling  

## 🔎 Closing Note

This analysis demonstrates that medical appointment no-shows are not random events — they are structurally and behaviorally predictable.

Three core findings emerge:

- 📌 **Behavior persists**: Prior no-show history materially increases future no-show probability.
- 📌 **Booking horizon matters**: Longer lead times significantly amplify risk.
- 📌 **Intervention works — but selectively**: SMS reminders reduce risk, yet coverage gaps and structural exposure limit overall impact.

From an operational perspective, the implication is clear:

> Risk should be managed proactively, not reactively.

Rather than applying uniform interventions, healthcare providers can:

- Target high-risk behavioral segments
- Prioritize long-lead appointments
- Optimize reminder coverage
- Design differentiated intervention strategies

The framework used in this dashboard — longitudinal reconstruction, relative risk modeling, and interaction analysis — provides a scalable template for predictive risk monitoring in appointment-based systems.

This project reflects a data engineering–driven analytical approach:  
build structure first, measure precisely, then intervene intelligently.

---

## Author

**Doobem**  
Data Analyst  

- LinkedIn: [@doobemoguzie](https://www.linkedin.com/in/prosper-oguzie-54a706336) 
- GitHub: [@Doobemoguzie](https://github.com/Doobemoguzie)
- Contact: [Prosperoguzie379@gmail.com](prosperoguzie379@gmail.com)




