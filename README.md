
# HR Analytics Dashboard

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiNWI3N2JhMTEtMTg3My00NDE1LWI4N2YtZTkzMTdkNjg5OWVkIiwidCI6IjhjYTA1MzkxLWJlNjYtNDk5Zi1iMTg1LTZkYjI4YTJlNmMwYiJ9

## Problem Statement

This dashboard helps the company understand their employees attendance performace better. It helps the company know if their employees prefer working from home or in the office according to the days of the week. Through different employee attendace record, they get to know their Human Resource strategies and plans. It also lets them know the employee present percentage and sick Leave percentage by the dates, thus since by using this dashboard they have identified that sick leave percentage was highest in the month of May.

Since, the work from home percentage is highest on Friday for all the three months with the average of (around 13%), thus in all they must look into this aspect while builing their HR strategies and plans.

Also since the sick leave percentage is highest on Monday & Thursday, thus they must try to reduce it.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : For calculating the employee present percentage for the months, null values were not taken into account as only less than 3% values are null in that column.
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : Since the data contains various attendace records and categories, thus in order to represent thoem, new visuals were added.
- Step 8 : Visual filter (Slicer) was added for the months which are "Apr 22", "May 22" and "Jun 22".
- Step 9 : Calculated count columns were created named "WFH Count", "SL Count", "Day of week", "WeekdayNum", "Month".

For creating new columns following DAX expression was written;
       
        WFH Count = SWITCH(TRUE(), 'Final Data'[Value] = "WFH", 1, 'Final Data'[Value] = "HWFH", 0.5, 0)

        SL Count = SWITCH(TRUE(), 'Final Data'[Value] = "SL", 1, 'Final Data'[Value] = "HSL", 0.5, 0)

        Day of week = FORMAT('Final Data'[Date], "ddd")

        WeekdayNum = WEEKDAY('Final Data'[Date])

        Month = STARTOFMONTH('Final Data'[Date])
        
Snap of new calculated columns ,

![Snap_1](https://github.com/Sid-Gogia-007/Bike-Share-Marketing-Analytics-Report/assets/155529593/c776d561-1a42-4d9e-8c4b-8b74f2cf8d51)

- Step 10 : Two column charts were also added to the dashboard representing the employees work from home percentage & sicke leave percentage by the days of the week.
           
           Although, by default, while calculating average, total employee present, sick leave and work from home percentage blank values are ignored.
- Step 11 : One area chart and one line chart was also added to the report design area representing the employee present and sicke leave percentage by date respectively.
- Step 12 : Visual cards were also added representing the total working days, total present days, employee present percentage, work from home percentage, sick leave percentage.
- Step 13 : In the report view, under the insert tab, a text box was added to the canvas, which stated the dashboard brief description.
- Step 14 : A visual (slicer) was also added to the dashboard which filers the visuals and insights according to the employee names data. 

- Step 15 : The report was then published to Power BI Service.
 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard_upload](https://github.com/Sid-Gogia-007/Bike-Share-Marketing-Analytics-Report/assets/155529593/0564db3d-38b3-4ee7-90c4-cec99b50cf93)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

(1) We can clearly see that the sick leave percentage is highest on Monday & Thursday.

(2) The work from home percentage is highest on Friday for all the three months with the average of (around 13%).

(3) By seeing the charts in the dashboard,  we can also say that it is clearly evident that the sick leave percentage had rapidly increaded since April 2022.
