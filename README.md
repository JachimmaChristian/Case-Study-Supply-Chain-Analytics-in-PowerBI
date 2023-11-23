# Supply Chain Analytics in PowerBI
In this project, I performed a Make vs Buy analysis in PowerBI. Before I dive into the project let me explain Supply Chain  and what Make vs Buy means so you'll be properly carried along.

Supply Chain is the network of individuals and companies that are involved in making a product and delivering it to the consumer and the Make vs Buy decision is choosing either to create a product in-house or to purchase it from an external supplier. Now we have these definitions out of the way lets dive right in!

## The Problem
The problem I worked on in this case study was to analytically determine a Make versus Buy decision for a fictitious company Tanate Industries that sells replacement parts for industrial pizza ovens. My task was to calculate the full cost of the Make and Buy Options so that the business could make an informed decision.

## Datasets and Data Model
The other analysts on the team started a PowerBI file by loading the data and creating a model but they need my help visualizing and interpreting the results.

![supply chain model](supplychain1.png)

## Data Transformation
The Quotes dataset is the supplier's price commitments for certain products and volumes. They say "If you buy X volume of this product you will pay 'Unit Cost' per unit and a one-time cost equal to 'Non-recurring-expenses'. A Quote is specific to a product, volume and supplier. 

We begin our transformation here by setting the volume column default summarization to 'Don't summarize' as PowerBI will automatically sum it up as its a numeric field.

Let's look at selecting a supplier, supplier selection is an important part in the Buying option, and cost is an important factor to be considered, let me introduce the concepts of unit cost, extended cost and full cost and how they affect the supply chain decision-making process.

Unit cost refers to the cost of purchasing an additional unit and includes the manufacturer's raw material cost, production costs, and profit.

Extended cost represents the cost paid for the products only and does not include one-time expenses. Extended cost is the number of units purchased multiplied by the unit cost.

Non-recurring cost is a one-time cost that must be paid to facilitate production.

Full cost represents the total amount a company must pay to buy a certain quantity of products. Full cost is the sum of the extended cost and the non-recurring expenses.

![adding new columns to the Quotes table](supplychain2.png)

Continuing in our data transformation exercise I created two new columns (Extended cost and Full cost) in the Quotes Dataset because we need the full cost values in order to inform our purchasing decision. I formatted the newly created columns to currency with 2 decimal places and set the default summarization to 'Don't summarise'.

## Data Visualization
For our first visualization, our manager has requested a report that shows: 

The supplier name with the lowest full cost for a part number and quote volume combination.

Visibility to the all of the other supplier quotes and full cost for the part number. 
