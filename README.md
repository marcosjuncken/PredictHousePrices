# Predict House Prices

## Table of Contents

1. [Installation](#Installation)
2. [Project Motivation](#Project-Motivation)
3. [File Descriptions](#File-Descriptions)
4. [Results](#Results)
5. [Licensing, Authors, and Acknowledgements](#Licensing-Authors-and-Acknowledgements)

## Installation

The following python libraries are used on the project: pandas, numpy, matplotlib, seaborn and sklearn.

## Project Motivation

For this project, I wanted to begin to apply some of the Machine Learning concepts and CRISP-DM process that I'm learning on Udacity Data Scientist Nanodegree, but in a subject that was interesting to me. 

Since the CRISP-DM methodology provides a structured approach to the project, I used this to develope this project and I will exlpain here:

### - Business Understanding

One thing that is very difficult at the real state market, is to understant what is a good price for each new property that a owner wants to sell. So one thing that I want to know is how to predict house prices? Is that possible using the concepts that I've already learned?
But following this question, which variables impact more in rent and in sales? Because probably they are different since the people that choose between these 2 different types of negotiation have different needs, maybe long terms and short terms needs?
It's common sense that the region where is the property located affects the price — so, this is our third question, where in São Paulo is cheaper and where is more expensive? This is really the variable most important?

So, these are our 3 questions to answer:

- How we can get at least 0.90 r² in a model to predict property prices?
- What neighborhoods in São Paulo have the highest squared meter price? And the lowest?
- Rent vs Sale: what is the difference between variables correlation with price?

### - Data Understanding

To answer that questions I needed to find a database that helped me with that. So I used [Sao Paulo Real Estate - Sale / Rent - April 2019](https://www.kaggle.com/argonalyst/sao-paulo-real-estate-sale-rent-april-2019) database that is on Kaggle. 

We have 13640 lines in the database and 16 columns for each respective variable: Price,	Condo	Size,	Rooms, Toilets, Suites,	Parking,	Elevator,	Furnished,	Swimming Pool,	New,	District,	Negotiation Type,	Property Type,	Latitude and Longitude.

You can check everything that I did on the first section of the Jupyter Notebook: A look into the data and data cleaning. 

### - Prepare Data

So I checked all the database and the main thing that I needed to do to prepare the data was: classify some of the columns as integers instead of boolean and fix Latitude and Longitude that was out of São Paulo.

You can check everything that I did on the first section of the Jupyter Notebook: A look into the data and data cleaning. 

### - Data Modeling

So to answer our questions we needed a loft of data modeling:

- How we can get at least 0.90 r² in a model to predict property prices?
Here I tried to predict using Linear Regression Model and I was not succesful, but after using Gradient Boost Model we could achieve the result here.

- What neighborhoods in São Paulo have the highest squared meter price? And the lowest?
This part was easier, I needed just to create a new column for properties for rent and for sales dataframes showing the squared meter price. After that, I created some tiles that could help us answering this questions. 

- Rent vs Sale: what is the difference between variables correlation with price?
I finded 2 ways to answer this question: a heatmap indicating the correlation of the variables with the price and measure the coefficient weights in a Linear Regression model.

You can check everything that I did on the questions sections of the Jupyter Notebook.


### - Evaluate the Results

The findings are explained on the Jupyter Notebook and on [this Medium Post](https://juncken-marcos.medium.com/how-can-we-predict-house-prices-with-machine-learning-f26b9432a7aa).

But here I will explain in a short summary:

- How we can get at least 0.90 r² in a model to predict property prices?
Yes it's possible using Gradien Boost Model, reaching 0.93 clf score.

- What neighborhoods in São Paulo have the highest squared meter price? And the lowest?
Highest Squared Meter Price - We have 9 districts that are in both lists: Iguatemi, Vila Olimpia, Itaim Bibi, Brooklin, Pinheiros, Vila Madalena, Moema, Campo Belo and Jardim Paulista. Alto de Pinheiros is just in the 10 highest Squared Meter Price for sale and Consolação is just in the 10 highest Squared Meter Price for rent.
Lowest Squared Meter Price - We have 5 districts that are in both lists: Grajaú, Artur Alvim, Itaim Paulista, Lajeado and Guaianazes. Capão Redondo, Medeiros, Itaquera, São Rafael and Cidade Tiradents are just in the 10 lowest Squared Meter Price for sale. Ponte Rasa, Jardim Helena, Jaçanã, José Bonifácio and Jardim São Luis are just in the 10 lowest Squared Meter Price for rent.

- Rent vs Sale: what is the difference between variables correlation with price?
Looking to the heatmap at the Notebook, we can see the variables that impact more when the apartment is for sale: size, number of rooms, toilets, and parking spots.
And the variables that impact more when the apartment is for rent: the condo price and if the apartment is furnished.
Bringing that to reality makes sense because the variables with a bigger correlation in the properties for sale are more about long-term characteristics and in the properties for rent is more about short-term characteristics.

When we look to the coefficient weights, we can understand that Geographic Location is the more important characteristic to define the price, which is very true. We can see this difference when we analyzed the Districts with the highest and lowest squared meter price. Suites and Furnished have a bigger impact on price when we look at the properties for sale. New and Toilets have a bigger impact on price when we look at the properties for rent.

## File Descriptions

The repository contains the database and the Jupyter Notebook with the analysis and findings about the 3 questions above.

## Results

The findings are explained on the Jupyter Notebook and on [this Medium Post](https://juncken-marcos.medium.com/how-can-we-predict-house-prices-with-machine-learning-f26b9432a7aa).

## Licensing, Authors, and Acknowledgements

The database used on this project was downloaded [here](https://www.kaggle.com/argonalyst/sao-paulo-real-estate-sale-rent-april-2019). Feel free to use the code available on this project.
