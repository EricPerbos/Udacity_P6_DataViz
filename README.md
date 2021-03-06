# Tesla Motors: impact of fiscal incentives on sales 
_by Eric Perbos-Brinck in fulfillment of Udacity’s [Data Analyst NanoDegree](https://www.udacity.com/course/data-analyst-nanodegree--nd002) (DAND), Project 6_  
_Email: eric.perbos.brinck@insead.edu_
</br>

####Current active version -> [Tesla Motors: a dramatic example of fiscal incentives on sales figures](https://bl.ocks.org/EricPerbos/raw/3f4f1f4d637a131376e8a11886fee51d)

#### Summary
Tesla Motors is a North American car company that designs, manufactures and sells electric vehicles all over the world (Wikipedia).

Providing an explicit picture of its European sales though one chart is intricate as countries vary widely in terms of absolute sales (from 25 to 2500 in a quarter), making a bar chart inadequate as one leading country will "dwarf" smaller ones in scale.

After initial research, I opted for circle's area as representation of sales.</br>After feedback, I added a small bar chart to show the "Sales per million of habitants" to show the local performance of each country marketwise.


#### Design
Bar/column and line charts are useful to compare sales over time between several regions of similar size. But if you have more than five regions or the min-max values are disparate (ex: factor 1 to 10), they become overloaded and difficult to read.

In this project, we strongly exceed those limits with  12 countries with min-max values of 2 (Finland Q4-2013) and 2,086 (Norway Q1-2014).</br>Here's an exemple of column chart which demonstrate the issue.
<a href="http://tinypic.com?ref=2n0k8s2" target="_blank"><img src="http://i63.tinypic.com/2n0k8s2.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

I researched through different business publications and found an example with circle size to be a better option, although with one potential pitfall due to the formula used to calculate its size or more accurately its area = Pi * r².</br>For example, a data value of 4 will create a circle with an area 16π.</br>A data value of 5 will create a circle with an area of 25π.

</br>This was brought to my attention during Udacity Data Visualization class, <b>Lesson 8.23 "How to lie with circles"</b> and the article [False Visualizations: When Journalists Get Data Viz Wrong](http://www.huffingtonpost.com/randy-krum/false-visualizations-when_b_5736106.html).</br>We followed the same principle by using <b>d3.scale.sqrt()</b> to get the square root of data values to determine the radius of each circle.


#### First draft and feedback

<a href="http://tinypic.com?ref=2rxzeyo" target="_blank"><img src="http://i65.tinypic.com/2rxzeyo.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

<b>Feedback by Tesla shareholder #1:</b> "It's a nice visualization but why do you choose so many different colors so light on white background ? Also the name of countries on the right is counterintuitive"

<b>Change #1:</b> I switched the names to the right and opted for a dual color based on TeslaMotors.com's colors.


#### Second draft and feedback

<a href="http://tinypic.com?ref=2poyu7l" target="_blank"><img src="http://i67.tinypic.com/2poyu7l.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

<b>Feedback by Tesla shareholder #2:</b> "The use of different diameter circles to signify volume is pretty clear (...) </br>Thinking about it a bit more, I think the strength of this dot graph is to show much more data points at the same time without losing track of which data point represents a certain country (...)</br>Also it seems the biggest sales are not located in largest countries, could you indicate the population size maybe ?"

<b>Change #2:</b> I added a small bar chart on the right, first with percentage of population vs. total population.</br>Later I realised that there was no obvious link between the two, Sales on one side, Population on the other.</br> So I computed a ratio "Sales per 1 million habitant" and changed the ranking order from alphabetical to Sales_per_1M_Hab, decreasing.


#### Third draft and feedback

<a href="http://tinypic.com?ref=10mr4zm" target="_blank"><img src="http://i68.tinypic.com/10mr4zm.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

<b>Feedback by Tesla shareholder #3:</b> "I think that the circles are an effective use of real estate given how many countries are listed and the marked differences in sales in each. </br> If one were to compare Norway's sales to Italy, the real estate used on the graph by Norway would push Italy off the page.</br>The circles, in my mind's eye, are essentially looking at the bar graph from above. The bigger the bar, the closer it is to me, and larger and easier to see.</br>I like how at the end, Eric does use the bar chart to show sales per million inhabitants. It provides a nice juxtaposition of the bar graph in relation to the circles.</br>Overall I found the graphic very informative and useful to show how government incentives and changes affect Tesla sales in Europe (see Denmark)."


#### Ressources

##### Project Evaluation Grid
<a href="http://tinypic.com?ref=309h9ip" target="_blank"><img src="http://i68.tinypic.com/309h9ip.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

https://teslamotorsclub.com/tmc/threads/tesla-europe-registration-stats.61651/</br>
http://bl.ocks.org/d3noob</br>
http://www.huffingtonpost.com/randy-krum/false-visualizations-when_b_5736106.html</br>
https://docs.google.com/spreadsheets/d/1hRFvUhAVi7UUP15rBcAU1W-_LGqnz3fNi3bKUqTeS-Q/edit#gid=0</br>
http://neuralengr.com/asifr/journals/
https://github.com/irenatrend/Data_Visualization_And_D3js_Udacity


