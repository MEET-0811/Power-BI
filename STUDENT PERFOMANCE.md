# 📊 Student Performance Dashboard (Power BI)

## 📌 Project Title
**Student Performance Dashboard – Academic & Behavioral Insights**

---

## 📖 Overview
This project is an interactive Power BI dashboard designed to analyze student performance across academics, attendance, and behavior. It provides meaningful insights using data visualization and DAX.

---

## 🎯 Objectives
- Analyze academic performance of students  
- Track attendance percentage  
- Monitor behavior patterns  
- Classify student performance (High / Medium / Low)  
- Build an interactive dashboard  

---

## 📂 Dataset

### 🧑 Students.csv
- StudentID  
- Name  
- Gender  
- Class  
- Section  

### 📊 Scores.csv
- StudentID  
- Subject  
- ExamType  
- Score  
- MaxScore  
- Term  

### 📅 Attendance.csv
- StudentID  
- Date  
- Status (Present/Absent)  
- Reason  

### 🧠 Behavior.csv
- StudentID  
- Date  
- BehaviorType  
- Notes  

---

## 🧩 Data Model
- Star Schema used  
- Relationships created using **StudentID**
- One-to-Many relationships:
  - Students → Scores  
  - Students → Attendance  
  - Students → Behavior  

---

## 🧮 DAX Measures

DAX
% Score = 
DIVIDE(SUM(Scores[Score]), SUM(Scores[MaxScore]))

Avg Score = 
AVERAGE(Scores[Score])

Attendance % = 
DIVIDE(
    CALCULATE(COUNTROWS(Attendance), Attendance[Status] = "Present"),
    COUNTROWS(Attendance)
)

Behavior Count = 
COUNT(Behavior[BehaviorType])

Performance Category = 
SWITCH(
    TRUE(),
    [% Score] >= 80, "High",
    [% Score] >= 40, "Medium",
    "Low"
)

## 📊 Visualizations

📌 Bar Chart → Average Score by Subject

<img width="398" height="197" alt="image" src="https://github.com/user-attachments/assets/945e8c41-be56-499d-be54-4fa5598132f5" />


📈 Line Chart → Performance Trend by Term

<img width="406" height="194" alt="image" src="https://github.com/user-attachments/assets/e3ed30fc-0464-452e-aba9-e28cebf1040c" />

🍩 Donut Chart → Behavior Distribution

<img width="408" height="199" alt="image" src="https://github.com/user-attachments/assets/7b0cd17b-b044-4cf8-ab49-c9dd45c5b751" />

📋 Table → Student Performance Summary

<img width="396" height="195" alt="image" src="https://github.com/user-attachments/assets/68d9ace9-e400-4a6e-934e-9af223ee8764" />

🔢 KPI Cards:
Total Students
Average Score
Attendance %

<img width="332" height="75" alt="image" src="https://github.com/user-attachments/assets/187ec4b2-b7d4-4dd8-8ba2-dd12e142d0ac" />

 ## DASHBOARD

<img width="898" height="474" alt="image" src="https://github.com/user-attachments/assets/266f42bc-1c91-4a44-9579-c81d07e7bb82" />

## 🎛️ Interactivity

## 🎯 Slicers:

Class

Section

Subject

Term

<img width="470" height="66" alt="image" src="https://github.com/user-attachments/assets/b57c69b7-75e9-474a-be5b-edeaa6d66218" />

## 🔍 Drillthrough:

Student-wise detailed page

## 🧾 Tooltips:

<img width="194" height="146" alt="image" src="https://github.com/user-attachments/assets/285203e0-a030-4cf4-8930-a6ce2bfbe1f1" />

Quick insights

<img width="838" height="483" alt="image" src="https://github.com/user-attachments/assets/87d200f5-c101-41a0-9d64-c417782940bf" />

## Video Link
https://drive.google.com/file/d/1qi4F_lQ81XblB2DRa0xZ6o8bLTYY8Wdd/view?usp=sharing
