# House Rocket
<p align="center">
  <img src="./rocketlogo.png" />
</p>

This is an *exploratory data analysis (EDA)* project whose objectives are to generate insights to answer two simple questions asked by a fictitious real estate company: given a list of properties, 1. which ones should be acquired and 2. what are the sales conditions to obtain the highest profit.

## 1.0. - Introduction
### 1.1. - Project Description:
House Rocket is a fictitious real estate company that profits from buying and selling properties, having as its main strategy to buy houses in good condition for a low price and sell them for a higher price. To maximize efficiency in the search for the best market opportunities and get a better notion of which prices to apply on top of the properties bought, the company requested this project using Data Science tools to generate insights through data manipulation and consequently help the best decisions of the business team.

With exception to the data collected from our database, the elements presented here are not real and serve only to create a context for the questions that a supposed CEO from a fictional company, House Rocket, is making to us. The questions about his business problems should be answered through our data analysis, which is the objective of this project. For the purpose of this project, we collected data from a public dataset published on Kaggle (House Sales in King County, USA) including homes sold between May 2014 and May 2015.

### 1.2. - House Rocket Visualization App:
To visualize and interact with the data we will be reporting here, please, feel free to follow the link below and have access to our dashboard:

[House Rocket Dashboard](https://pgdemiranda-houserckt-app-96abf5.streamlitapp.com/)


## 2.0. - Analysis Plan
### 2.1. - Business Questions:
Our client, the CEO of House Rocket, e-mailed us 2 questions:
1. Which properties should House Rocket buy and for what price?
2. Once the houses are acquired, when is the best time to sell them, and for what price?

### 2.2. - Final product: 
An e-mail containing:
- A link to the [dashboard](https://pgdemiranda-houserckt-app-96abf5.streamlitapp.com/).
- Two csv files attached, each one answering the questions.

### 2.3. - Tools used:
1. Python 3.9.13
2. VS Code
3. Jupyter Notebook
4. Streamlit
5. Streamlit Comunity Cloud

### 2.4. - Schedule of Operation:
1. Business comprehension (explained on our contact with House Rocket CEO)
2. Defining which tools are necessary to build our final products (item 2.3.)
3. Importing and cleaning data
4. Analyzing data
5. Creating and testing hypotheses
7. Development and deployment of the final products


## 3.0. - Importing and Cleaning Data
### 3.1. - House Sales in King County, USA:
https://www.kaggle.com/datasets/harlfoxem/housesalesprediction

### 3.2. - Dataset Attributes:
The dataset collected from Kaggle contains 21 different attributes which are described as follows:

- **id**: unique ID for each home sold.
- **date**: date of the home sale.
- **price**: price of each home sold.
- **bedrooms**: number of bedrooms.
- **bathrooms**: number of bathrooms, where .5 accounts for a room with a toilet but no shower.
- **sqft_living**: square footage of the apartments interior living space.
- **sqft_lot**: square footage of the land space.
- **floors**: number of floors.
- **waterfront**: a dummy variable for whether the apartment was overlooking the waterfront or not.
- **view**: an index from 0 to 4 of how good the view of the property was.
- **condition**: an index from 1 to 5 on the condition of the apartment.
- **grade**: an index from 1 to 13, where 1-3 falls short of building construction and design, 7 has an average level of construction and design, and 11-13 have a high quality level of construction and design.
- **sqft_above**: the square footage of the interior housing space that is above ground level.
- **sqft_basement**: the square footage of the interior housing space that is below ground level.
- **yr_built**: the year the house was initially built.
- **yr_renovated**: the year of the house’s last renovation.
- **zipcode**: what zipcode area the house is in.
- **lat**: lattitude.
- **long**: longitude.
- **sqft_living15**: the square footage of interior housing living space for the nearest 15 neighbors.
- **sqft_lot15**: the square footage of the land lots of the nearest 15 neighbors.

For the description of these attributes, we consulted the links below:
- https://www.kaggle.com/datasets/harlfoxem/housesalesprediction/discussion/207885
- https://www.slideshare.net/PawanShivhare1/predicting-king-county-house-prices

### 3.3. - Assumptions:
While exploring this dataset, we assumed that:
1. The value "0" in yr_renovated are houses that have never been renovated.
2. The value "33" displayed in the bedroom column was considered an error and was dropped out.
3. The price column means the price the house was or will be bought by the company House Rocket.
4. Duplicate IDs were removed and only the most recent sale was considered.
5. The values in the 'condition' column were classified as bad (1 and 2), regular (3 and 4) and good (5).
6. The values in the 'view' column were classified as bad (1), good (2 and 3) and excellent (4). The properties whose "view" value were "0", were considered to have no impact on the final value of the property, therefore classified as "null".
7. Location and condition of the property were the decisive characteristics in buying or not buying the property.
8. The season of the year was the decisive characteristic for the time of sale of the property.


## 4.0. - Hypotheses (Creating, Data Manipulation and Hypothesis Testing)
### 5 key insights from this project
- H1: The average price of properties that have a water view are, at least, 30% higher.
**True**: properties with water view have their average price 30% higher.

- H2: The average price of properties built before 1955 is, at least, 50% cheaper.
**False**: the average prices of properties built before and after 1955 are very close (with a difference of 0.62%).

- H6: The average price fluctuates by 20% between property conditions.
**False**: although properties in bad conditions (1 and 2) and good conditions (3 and 4) have similar average prices, the difference on the average price between them is more than 60%.

- H7: Properties that never went through renovations are, at least, 40% cheaper.
**True**: properties without any renovation are 40% cheaper. 

- H10: Overall, there is a devaluation of these properties during winter time.
**True**: it would be ideal to buy properties during winter to sell during spring or summer. 

The entire process of manipulating and visualizing the data, as well as the tests of our hypotheses can be found in the [project notebook](./house_rocket.ipynb).

## 5.0. - Dashboard and csv files
The dashboard was deployed on Streamlit Comunity Cloud and this is the link we can provide to our client: https://pgdemiranda-houserckt-app-96abf5.streamlitapp.com/

The csv files contains a [recomendation of 157 properties that could be bought by House Rocket](./to_buy.csv) and [the best selling conditions to achieve the highest profit margin](./to_sell.csv) according to our data.


## 6.0. - Concluding Thoughts
The objectives that were initially established have been met. 
We answered both questions by delivering two csv files containing a list of 157 properties that can be acquired at a reasonable price by the company and sold in different seasons making a good profit. 
If House Rocket can acquire and sell all the suggested properties, it can expect a total profit of **US$24222890.20**

From here, this project can be refactored according to new parameters. Among the possibilities, the most interesting is the use of Machine Learning. This work can be done not only by revisiting all the steps of this project with more data and business understanding, but also by studying and evaluating the algorithms that can best deliver me a Machine Learning model that fits the evaluation we are looking for.
