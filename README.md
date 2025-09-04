# GTC ML Project 1 – Hotel Booking Data Preprocessing

## 📌 Project Overview
This project focuses on preparing raw hotel booking data for a **cancellation prediction model**.  
The goal is **not** to build the model itself, but to ensure the dataset is clean, consistent, and machine-learning ready.  

Cancellations have a major impact on hotel profitability, and this project delivers a structured **data preprocessing pipeline** that ensures better model performance in the future.  

---

## 🚀 Project Phases

### **Phase 1: Exploratory Data Analysis (EDA)**
- Generate summary statistics (`.describe()`, `.info()`).
- Identify missing values and visualize patterns (missingno matrix, heatmaps).
- Detect outliers in key columns (`adr`, `lead_time`) using boxplots and IQR method.
- Document key data quality issues.

### **Phase 2: Data Cleaning**
- **Handle Missing Values**:
  - `company`, `agent` → Replace with `"None"` or `0`.
  - `country` → Impute with mode or `"Unknown"`.
  - `children` → Impute with median/mode.
- **Remove Duplicates**: Drop exact duplicate rows.
- **Handle Outliers**: Cap extreme values (e.g., `adr > 1000 → 1000`).
- **Fix Data Types**: Format date columns correctly.

### **Phase 3: Feature Engineering & Preprocessing**
- **New Features**:
  - `total_guests = adults + children + babies`
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`
  - `is_family` → Binary flag (`Yes/No`) if children or babies included
- **Encode Categorical Variables**:
  - One-Hot Encoding for low-cardinality (`meal`, `market_segment`).
  - Frequency encoding or grouping for high-cardinality (`country`).
- **Prevent Data Leakage**:
  - Drop `reservation_status` & `reservation_status_date`.
- **Final Dataset Split**:
  - Train/Test split (80/20, `random_state=42`).

---

## 🛠 Tech Stack
- **Python**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn, Missingno
- **Data Processing**: Scikit-learn

---

## 📂 Dataset
- **Source**: `hotel_bookings.csv` (raw PMS export)
- **Target**: ML-ready dataset for cancellation prediction

---

## 🎯 Objective
Deliver a **robust data preprocessing pipeline** to ensure reliable input for machine learning models.  
The quality of this pipeline directly impacts the hotel’s ability to reduce losses from last-minute cancellations.  

---

## 👨‍💻 Author
- **GTC Team**
