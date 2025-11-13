---
layout: page
title: "HW5.1 – Licenses Visualizations"
permalink: /hw5-1/
---

# HW5.1 – Licenses Visualizations

For this homework, I used the **Illinois Licenses Dataset** (`licenses_fall2022.csv`) from the IS445 data repository.  
I created two visualizations: one simple bar chart and one interactive time-based plot.

---

## Plot 1 – Top 15 License Types (Bar Chart)

<iframe src="/assets/hw5-1/licenses_plot1.html" 
        width="100%" height="450" style="border:none;"></iframe>

### Description  
This plot shows the **top 15 most common license types** in the dataset. Each bar represents a license category, and the x-axis shows how many licenses fall under that category. This visualization helps quickly identify which license types appear most frequently.

### Design choices – Encodings  
A **horizontal bar chart** was used because long category names are easier to read when placed on the y-axis.  
- **Y-axis (nominal)** → License Type  
- **X-axis (quantitative)** → Count of licenses  
Tooltips were added for clarity, allowing users to check exact values.

### Design choices – Color  
I used a **single, consistent color** for all bars. Since the main purpose is to compare magnitudes, adding multiple colors would distract more than help. A uniform color keeps the visual focus on the ranking.

### Data transformations  
In the Python notebook, I:  
1. Grouped data by `License Type`  
2. Counted the number of records in each category  
3. Selected the top 15 categories  
4. Sorted them in descending order  
This reduces noise from rare license types and highlights the major categories.

---

## Plot 2 – Monthly Licenses by License Type (Interactive Line Chart)

<iframe src="/assets/hw5-1/licenses_plot2.html" 
        width="100%" height="450" style="border:none;"></iframe>

### Description  
This plot displays **how many licenses were issued each month**, for a license type selected from a dropdown menu. The plot updates dynamically based on user choice, allowing exploration of trends over time.

### Design choices – Encodings  
A **line chart** with points was used to show temporal trends:  
- **X-axis (temporal)** → Month  
- **Y-axis (quantitative)** → Number of licenses  
- **Tooltip** → Month, count, and selected license type  
A single line color was kept to avoid unnecessary visual clutter.

### Design choices – Color  
The line uses one fixed color because the dropdown already controls which license type is being viewed. Using multiple colors for different categories would not improve the visualization, since only one category is visible at a time.

### Data transformations  
In the notebook, I:  
1. Converted `Original Issue Date` to datetime  
2. Extracted a `month` variable (rounded to first day of month)  
3. Aggregated counts by `month` and `License Type`  
This preprocessing smooths daily noise and highlights month-to-month patterns.

---

## Interactivity

The second plot includes a **dropdown menu** that lets the user select a specific license type.  
This interactivity makes the visualization far clearer:

- The viewer can compare temporal trends without overlapping multiple lines  
- The graph remains clean and readable  
- The user can explore patterns across categories without extra clutter  

This interactive element adds flexibility and enhances insight.

---

## Links

- **The Data:**  
  [licenses_fall2022.csv](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)

- **The Analysis (Python Notebook):**  
  [hw5_1_licenses.ipynb](https://github.com/jinujung1021/jinujung1021.github.io/blob/main/python_notebooks/hw5_1_licenses.ipynb)

