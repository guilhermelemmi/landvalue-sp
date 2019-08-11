#Using Foursquare to predict land prices in São Paulo
_Capstone project for the IBM Professional Data Science Certification program_

In this project we use Foursquare venue locations associated with publicly available land value data to create a model to predict land prices using Regression algorithms.

## Introduction 
It is known that close-by amenities can have an impact on land prices. This project intends to cross information already known from land prices in the city of São Paulo with Foursquare venue locations, in order to create a model capable of predicting land prices for a given location in the city.

The following objectives will be pursued by this work:

- Extract statistics and create land price visualizations from public available data on land value;
- Create a simple regression model to predict land prices based on this public data;
- Improve this model by adding venue locations extracted from the Foursquare API;
- Measure and compare the efficiency of each model.

The main beneficiaries from this report will be real estate investors and agents followed by anyone searching for a good place to live in the city. Also, it adds value to the Data Science community as a whole as the result of the conducted research will contribute to evaluate if the use of Foursquare data can benefit other land price prediction models.

## Data
To perform this research, two main datasets will be used:

Public data from São Paulo's city hall related with land value in the city
The city Hall of São Paulo has made available data regarding land taxes paid in the city. In this data there's also interesting data about the land value by m2 for different neighbourhoods in the city.

The table below is an example of this data, where columns "BAIRRO DO IMOVEL" and "VALOR DO M2 DO TERRENO" show neighbourhood and the land value by m2, respectively.

iptu_sample.png

Foursquare API to retrieve venue locations
Foursquare holds the location for venues in different categories (bars, cinemas, supermarkets, museums, etc).

## Methodology
The following steps were performed to arrive at the final results:

### Exploratory Analyses of the city data
São Paulo's city data was imported into a Jupyter notebook. It was then cleaned and transformed to remove irrelevant data (land owner's name, etc) or to combine redundant fields (`bare m2 price` and `constructed m2 price` were replaced by `m2 price`, the mean between both values).

After clean up, this dataset was explored by inspecting its data types, density and distribution. The following histogram shows the density and distribution of `M2 PRICE` values.

After initial inspection, it was inferred that variable `NEIGHBOURHOOD` could have a significant impact on the land prices, so the following Boxplot chart was created with `M2 PRICE` by `NEIGHBOURHOOD`.

After applying a simple Label Encoding technique that transformed categorical data such as neighbourhood and type into numerical values, the following correlation heat map matrix was produced, to reveal any possible correlations in our data.

With the same intent, a detailed scatter matrix was also produced with the data.

Visual inspection of this data did not indicate any strong correlation between our fields. Seems like `` could have a slight impact on land prices, so that was the feature chosen to create our first Simple Linear Regression model.

### Simple Linear Regression model design and evaluation

### Multiple Linear Regression model design and evaluation

### Exploratory Analyses of Foursquare data

### Simple Linear Regression with Foursquare's data model design and evaluation

### Multiple Linear Regression with Foursquare's data model design and evaluation

### Multiple Linear Regression model without Neighbourhood design and evaluation

### Multiple Linear Regression without Neighbourhood and with Foursquare's data model design and evaluation

## Results
The results obtained with each model were evaluated through Mean Square Error and Root Mean Square Error metrics, along with their R2 Score. These metrics were summarized in the table below:





## Discussion
The results show that 

This article was created for illustration purposes and designed to showcase routine operations on the day-to-day of a Data Scientist as the capstone of the IBM Professional Data Scientist Certification program. As such, it does not aim for accuracy and should not be interpreted without discretion.

Flawed data set for land value

no data set for neighborhoods, only districts

section where you discuss any observations you noted and any recommendations you can make based on the results.

## Conclusion
In this work we used public available data about the city of São Paulo combined with Foursquare venue's data in order to create a model to predict land value prices in this city.

The strategy was to first create a model using the data provided by São Paulo's city hall, containing the m2 price for millions of houses in the city along with other interesting information such as district, year of construction and number of floors.

To create this model we used both simple linear and multiple linear regression at first. The model was trained and its efficiency was measured.

Then, we extracted data from Foursquare API to obtain the main venues located close to each district centroid, we separated these venues according to their price range into two buckets  and incorporated this countage in our model, refitting and re-evaluating its efficiency.

The results obtained demonstrated that a single feature could drive predictions with the best accuracy: Neighbourhood. While using neighbourhood in our model, the data added from Foursquare did not increase our accuracy significantly.

On the other hand, in a scenario where neighbourhood would not be known, then Foursqure data proved to be of much value, increasing the accuracy from the model from ... to... (r2 score).

This results demonstrate that Foursquare can be a valuable source of information on the creation of Data Science models. Further work still needs to be conducted in order to improve the methodology used here and consequently improve the results obtained.
