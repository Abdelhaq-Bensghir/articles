# [Tableau] How to design a waterfall chart?

<img width="393" alt="tableau_waterfall" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/9b6e6f80-75f2-4498-9a68-7af20ede63e6">

## Introduction

For Tableau beginners, creating a waterfall chart can be challenging. In this tutorial, we'll walk through the steps using the 2017 version of the superstore Database. However, feel free to use any version, as we'll only need the [Order Date] and [Sales] fields.

<img width="393" alt="tableau_waterfall2" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/e7d89773-c45e-4f10-ba77-60a32d581fcf">

### Input Values

Our goal is to visualize the month-by-month evolution of sales in 2017. The chart will display gains in blue and losses in red.

<img width="393" alt="tableau_waterfall3" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/f2d2fda3-bdbb-4b7b-bda2-4d242a346374">

### Let's Get Started

**1st Step:** Drag the fields [Order Date] and [Sales] to the rows and columns, respectively. Apply a filter to show only 2017 orders.

<img width="393" alt="tableau_waterfall4" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/fda1ac47-63f6-4c17-a38f-1a0eba200f4a">

**2nd Step: Create a Gantt diagram.**

<img width="393" alt="tableau_waterfall5" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/e5a9b19d-a162-43dc-a30c-bc0dcff5b24f">

The trick now is to design bar plots that will start from those lines we have, to indicate what changes that occured between each month and the next one. So for January we need to have a blue bar telling that we gained 43971$. and for February, we will have a red bar telling that we lost 20301$ — 43971$= -23 670$.

1. A field [Difference] that will compute the difference between each month and the last month before it. This field will give to the first month by default its own value (since it has no month before it).

<img width="393" alt="tableau_waterfall6" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/6115a137-b798-4a72-bd55-a7d3c41a44fe">

2. A field [Color] that will precise if the difference registered is negative or positive. this takes simply the sign of the field [Difference]:

<img width="393" alt="tableau_waterfall7" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/590f45f3-88e7-4af1-bf8c-cee6d9ef0e07">

3. A field [Show difference] That will give out the size of the bars that will be plotted. the minus added to the output below is to precise if the bar will be plot up or down (since bar plots in tableau are plot upwards if the value is positive, and downwards if the value is negative).

<img width="393" alt="tableau_waterfall8" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/6546ec15-b902-4760-b89a-9f31e070b823">

We’re all set!

Now Let’s create a double axis graphic by adding again the field [Sales] to the rows as in (1). Then a window is added to the marks card (2) with the name SUM(Sales) (2).

Add to this window the three created fields as indicated. Please pay attention to add a minus ti the field [Show difference] after adding it as a label.

Then we get something like this :

<img width="393" alt="tableau_waterfall9" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/6024588e-a092-4765-b1d4-f094fc85738d">

We still need to create the line that will link the sales values of the different months. To do that, click on the first pane of the Marks card: SUM(Sales), click the dropdown menu and then select Line.

<img width="393" alt="tableau_waterfall10" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/decb20d2-7624-447a-83eb-f954c3e9fb12">

Then set the line type to ‘Step’ type. You will get the following :
<img width="393" alt="tableau_waterfall11" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/2096722e-fc06-4bad-ba71-9cf9e857d8bf">

You can also play with the size of the ligne to render it more light. Then the last step is to merge the two axis. This could be done in a variety of ways, but consider the following method, using Dual Axis option from the Rows:

<img width="393" alt="tableau_waterfall12" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/03cd6248-d8bc-4cf7-b70b-5eb51a33d751">

Then you’ll notice the graphic gets transformed to a dual axis graphic, but still we need to synchronise those two axis. So right click the right axis and select synchronise Axis option.

<img width="393" alt="tableau_waterfall13" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/b5405d9c-a699-4fb4-9e1c-442eed49d627">

Now, remove the labels for the line plot, and hide the header of the second Sales axis at the right, and you finally get the Viz we intended to create:

<img width="393" alt="tableau_waterfall14" src="https://github.com/Abdelhaq-Bensghir/articles/assets/34965389/79773c9f-70b1-40f8-b36c-8e724c8808b1">

### Conclusion

You've successfully created a waterfall chart in Tableau! If you found this helpful, let me know for more tutorials. Feel free to ask questions or connect with me on [Linkedin](https://linkedin.com/in/bensghir)!

See you next time.
