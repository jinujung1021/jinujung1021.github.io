---
layout: page
title: "HW5.1 – Licenses Visualizations"
permalink: /hw5-1/
---

# HW5.1 – Licenses Visualizations

For this HW5, I used the **Illinois Licenses Dataset** from `licenses_fall2022.csv`.  
I created two plots (1,2): one simple bar chart and one interactive time based plot.

---

## Plot 1 – Top 15 License Types (Bar Chart)

<iframe src="/assets/hw5-1/licenses_plot1.html" 
        width="100%" height="450" style="border:none;"></iframe>

### Description  
This plot 1 shows the top 15 most common license types in the dataset like it says on the title. So, basically giving a quick sense of which categories appear the most. I used a horizontal bar chart because some of the license names are pretty long and I thought tilting the names would be bad idea, + it’s just much easier to read. The encodings are simple: the y axis is the license type, the x axis is the number of licenses, and I left a default navy teal color, because we are just comparing the sizes. Not because I didn't know how to make it fancy and cool, just because using multiple colors would just distract from the EDA I did.

Before drawing the graph, I did little bit of fixing of date column, mainly because I needed it for my plot2. Order for me to make cool interactive plot2, the `Original Issue Date` column was stored as a string, so I first converted it into a datetime format. After that, I created a new “month” column by extracting the month portion of each date, since the second plot looks at how license counts change month by month. Even though this first plot does not use the date or month information, I kept these transformations in as part of my overall process. 



---

## Plot 2 – Monthly Licenses by License Type (Interactive Line Chart)

<iframe src="/assets/hw5-1/licenses_plot2.html" 
        width="100%" height="450" style="border:none;"></iframe>

### Description  
This plot 2 shows how the number of licenses changes over time for any selected license type. Before drawing the graph, I cleaned the date column by converting `Original Issue Date' like I have explained in above. X axis represents this month based time variable (the axis labels appear as years), and the y axis shows how many licenses were issued. I used a line chart with points(months) because I couldn't find any better way, and I thought spikes would be easy to tell in line graphs. 
As you can see I made a new `License_Type' column before making plot2. The original name has a space in it, just to avoids errors, and much more easier and simpler when building a plot. 
 
For design choices, I kept the color fixed as default one, since the dropdown menu would control which license type is being viewed. Adding more colors would make no sense but pretty. If you put cursor on the point you want to look at, the tooltip includes the month, the number of license ("# of licenses"), and the selected license type so we can check exact values.

Last but not least, main interactivity in plot2 is probably the dropdown menu that shows under all "license type" column. I believe this makes the visualization much more cooler because it avoids plotting dozens of overlapping lines and instead lets us to see each category individually.

---

## Links

**License Data:**  
  [licenses_fall2022.csv](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)
**(Python Notebook):**  
  [hw5_1_licenses.ipynb](https://github.com/jinujung1021/jinujung1021.github.io/blob/main/python_notebooks/hw5_1_licenses.ipynb)

