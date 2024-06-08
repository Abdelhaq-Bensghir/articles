# Creating a Waterfall Chart in Tableau

By Abdelhaq Bensghir

---

## Introduction

For Tableau beginners, creating a waterfall chart can be challenging. In this tutorial, we'll walk through the steps using the 2017 version of the superstore Database. However, feel free to use any version, as we'll only need the [Order Date] and [Sales] fields.

### Input Values

Our goal is to visualize the month-by-month evolution of sales in 2017. The chart will display gains in blue and losses in red.

### Let's Get Started

**1st Step:** Drag the fields [Order Date] and [Sales] to the rows and columns, respectively. Apply a filter to show only 2017 orders.

**2nd Step:** Create a Gantt diagram. In the Marks card, select Gantt Bar.

### Building the Chart

The trick is to design bars indicating changes between each month. To achieve this:

1. Create a field [Difference] computing the month-to-month difference.
2. Create a field [Color] to indicate if the difference is positive or negative.
3. Create a field [Show difference] to determine bar size.

### Creating the Graphic

1. Add [Sales] to the rows again.
2. Add a window to the Marks card with SUM(Sales).
3. Add the three created fields. Add a minus to [Show difference] as a label.

### Final Touches

1. Create a line connecting sales values of different months.
2. Set line type to 'Step'.
3. Adjust line size.
4. Merge the two axes using Dual Axis option from the Rows.
5. Synchronize the axes.
6. Remove labels for the line plot and hide the header of the second Sales axis.

### Conclusion

You've successfully created a waterfall chart in Tableau! If you found this helpful, let me know for more tutorials. Feel free to ask questions or connect with me on Linkedin!

See you next time!