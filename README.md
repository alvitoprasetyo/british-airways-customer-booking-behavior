# british-airways-customer-booking-behavior
Predictive modeling and exploratory data analysis on British Airways customer flight booking behavior.

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E.svg)](https://scikit-learn.org/)

## 📌 Business Overview
Understanding customer booking behavior is critical for airlines to optimize dynamic pricing, target marketing campaigns, and improve conversion rates. This project analyzes British Airways customer booking data to identify key patterns behind completed bookings (`booking_complete`) and builds a foundation for predictive modeling.

---

## 🎯 Key Objectives
1. **Analyze Conversion Drivers:** Uncover patterns and feature distributions that influence flight booking completions.
2. **Evaluate Ancillary Services:** Understand customer demand for add-ons such as extra baggage, in-flight meals, and preferred seating.
3. **Data Quality & Preprocessing:** Clean, deduplicate, and prepare raw customer data for robust machine learning models.

---

## 📊 Dataset Highlights
The dataset contains **50,000 records** representing customer flight searches and booking attempts across various routes and sales channels:

| Feature | Type | Description |
| :--- | :--- | :--- |
| `num_passengers` | Integer | Number of passengers traveling |
| `sales_channel` | Categorical | Channel used for booking (Internet, Mobile) |
| `trip_type` | Categorical | Type of trip (RoundTrip, OneWay, CircleTrip) |
| `purchase_lead` | Integer | Number of days between booking date and travel date |
| `length_of_stay` | Integer | Duration of stay at destination (days) |
| `flight_hour` | Integer | Hour of flight departure |
| `flight_day` | Categorical | Day of week of flight departure |
| `route` | Categorical | Flight route (Origin -> Destination) |
| `booking_origin` | Categorical | Country where the booking was initiated |
| `wants_extra_baggage` | Binary (0/1) | Flag for extra baggage request |
| `wants_preferred_seat`| Binary (0/1) | Flag for preferred seat request |
| `wants_in_flight_meals`| Binary (0/1) | Flag for in-flight meal request |
| `flight_duration` | Float | Total duration of the flight (hours) |
| `booking_complete` | Binary (0/1) | **Target Variable:** Booking completed (1 = Yes, 0 = No) |

---

## 💡 Key Insights & Findings
- **Low Overall Conversion:** Only **~15%** of recorded customer interactions resulted in a completed booking (`booking_complete = 1`), highlighting a significant class imbalance challenge.
- **High Demand for Extra Baggage:** Approximately **67%** of customers opt for extra baggage, making it the most popular add-on service, followed by in-flight meals (~43%) and preferred seating (~30%).
- **Booking Lead Time Distribution:** The average `purchase_lead` is ~85 days, with long-tail outliers (some bookings placed >800 days in advance).
- **Data Integrity:** Identified and removed **719 duplicate rows** to ensure clean training data and prevent data leakage.

---

## 🚀 Recommended Next Steps
- **Class Imbalance Handling:** Apply techniques like **SMOTE** or tune `scale_pos_weight` in tree-based algorithms.
- **Feature Engineering:** Aggregate historical route-level conversion rates and categorize lead times (e.g., Last-minute vs. Early-bird).
- **Model Experimentation:** Train and evaluate **Random Forest**, **XGBoost**, and **LightGBM** using **ROC-AUC** and **Precision-Recall AUC** metrics.

---

## 🛠️ Tech Stack & Tools
- **Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn
- **Environment:** Jupyter Notebook / Google Colab

---

## 📂 Repository Structure
```text
.
├── british-airways-customer-booking-behavior.ipynb  # Main EDA and modeling notebook
├── customer_booking.csv                            # Dataset
├── README.md                                       # Project documentation
└── .gitignore                                      # Files ignored by Git
