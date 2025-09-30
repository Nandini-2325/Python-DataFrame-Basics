# Python-DataFrame-Basics
# 🚗 Pandas Vehicle Dataset Analysis  

This repository contains exercises using **Pandas** to explore and analyze a vehicle dataset (`mpg.csv`). The goal is to practice **data exploration, Boolean operations, arithmetic calculations, and column manipulation** in Python.  

---

## 📌 Summary of Tasks

1. **Data Exploration**
   - Imported the CSV dataset into a Pandas DataFrame.
   - Explored the data using `.head()`, `.tail()`, `.describe()`, `.shape()`, `.mean()`, `.sum()`, `.value_counts()`, `.max()`, `.min()`, `len()`, and `.median()`.
   - Sorted values to inspect specific columns.

2. **Creating New Columns**
   - Created a Boolean column `is_automatic` indicating if a vehicle has an automatic transmission.
   - Added a calculated column `fuel_economy` as a **weighted average**:  
     `fuel_economy = (city_mpg * 0.55) + (highway_mpg * 0.45)`.

3. **Analysis Using Boolean Masking**
   - Used `is_automatic` to **count the number of automatic vehicles**.
   - Determined **percentage of subcompact vehicles**.
   - Filtered vehicles with `fuel_economy` **above the median** using Boolean masking.

---

## ⚡ Skills Practiced

- Importing and inspecting CSV datasets with Pandas.
- Exploring data with descriptive statistics and summary functions.
- Creating and manipulating **new columns** using arithmetic operations.
- Filtering and analyzing data using **Boolean masking**.
- Calculating percentages and weighted averages.
- Summarizing insights from the dataset effectively.

---

✨ *This exercise reinforces foundational Pandas skills for real-world data analysis and prepares for more advanced data manipulation tasks.*

---

## 1️⃣ Importing the CSV and Exploring the Dataset

import pandas as pd

### Load the dataset
mpg = pd.read_csv('mpg.csv')

### Display first few rows
mpg.head()

<img width="1111" height="205" alt="image" src="https://github.com/user-attachments/assets/6924b2aa-df5a-4ffe-922c-7a3ea54618ed" />

**Task:** Use the `is_automatic` column to find how many vehicles are automatic.  

### Sum the Boolean column to count automatic vehicles
mpg['is_automatic'].sum()

<img width="724" height="35" alt="image" src="https://github.com/user-attachments/assets/472ec747-f826-4c6d-accc-c71c4e3a393e" />

**Task:** Determine what percentage of vehicles are subcompacts.

### Count subcompact vehicles and calculate percentage
subcompact_percentage = mpg[mpg["class"] == "subcompact"]["class"].count() / len(mpg) * 100
subcompact_percentage
<img width="687" height="32" alt="image" src="https://github.com/user-attachments/assets/199b1a21-b371-474d-b722-bea4be512c8e" />

**Task:** Add a `fuel_economy` column as a weighted average of city and highway MPG (55% city, 45% highway).

### Calculate weighted fuel economy
mpg['fuel_economy'] = mpg['cty'] * 0.55 + mpg['hwy'] * 0.45

### Display first few rows to verify
mpg.head()
<img width="1222" height="197" alt="image" src="https://github.com/user-attachments/assets/83ffda13-b1ae-4f10-8d12-508d6192054f" />

**Task:** Use Boolean masking to find vehicles with `fuel_economy` above the median.

### Filter vehicles with fuel_economy above the median
high_fe_vehicles = mpg[mpg.fuel_economy > mpg.fuel_economy.median()]

### Display first few rows
high_fe_vehicles.head()
<img width="1215" height="393" alt="image" src="https://github.com/user-attachments/assets/a6023026-4669-4169-a806-b5087b576468" />


