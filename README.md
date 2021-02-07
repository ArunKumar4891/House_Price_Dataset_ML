# House_Price_Dataset_ML
House Price Analysis &amp; Predictions Using Machine Learning

#  House Price Analysis & Predictions Using Machine Learning

House Price Dataset where we predict the housing price (Sales data) for each Ground value through Python, Scikit-Learn (Machine learning).

# Pandas Profiling :
Pandas profiling is an open source module with which we can quickly performed Exploratory Data Analysis with just a few lines of code. Pandas profiling performed all the work of visualizing and understanding the distribution of each variable thus generating a report with all the utmost important information easily available.



FIGURE 1.1: Roadmap of the analyses carried out.

https://pbiecek.github.io/xai_stories/images/02-plan.png




Data
We analyzed the data, more. Data contains 19 house features plus the price and the id columns, along with 21613 observations. Below the Table 1.1 describes the variables in the data set.

TABLE 1.1: Description of variables in the dataset.
Variable	        Description
id	              unique ID for each house sold
date	            date of the house sale
price	            price of each house sold
bedrooms	        number of bedrooms
bathrooms	        number of bathrooms, where .5 accounts for a room with a toilet but no shower
sqft_living	      square footage of the apartments interior living space
sqft_lot	        square footage of the land space
floors	          number of floors
waterfront	      apartment was overlooking the waterfront or not
view	            how good the view of the property was
condition	        condition of the apartment
grade	            level of construction and design
sqft_above	      the square footage of the interior housing space that is above ground level
sqft_basement	    the square footage of the interior housing space that is below ground level
yr_built	        the year the house was initially built
yr_renovated	    the year of the house’s last renovation
zipcode	          zipcode area
lat	              lattitude
long	            longitude
sqft_living15	    the square footage of interior housing living space for the nearest 15 neighbors
sqft_lot15	      the square footage of the land lots of the nearest 15 neighbors



1.2.1 Data preperation
Original data from kaggle is in good quality at the start, but we needed to preprocess it to suit our needs. In this section we describe how we prepared ready-to-use text files of the train and test data (train.csv, test.csv). This includes variable transformations, joining external data, records processing.

Firstly, we discovered that there are houses that were sold twice, and one house that was sold three times. One can assume that it was bought, renovated and then sold for more. But they have the same explanatory variables, without changes. Each pair (or triple) representing the same house we decide to aggregate into a single row, averaging the price.

1.2.2 External data
We decided to add external data. We believe most variables describe the house properly. What we were missing is some spatial information. Except for zip code, we have information about longitude and latitude, but we wanted to explain it in more detail. Why do some locations tend to be more expensive? Maybe it is because of public transport availability. That is why we decided to add a variable describing a distance to the nearest bus or subway stop. Data sources can be found here.

There might also be another reason. Maybe some houses are more expensive, because of some interesting places around, like museums, galleries or fine restaurants. Let us call them cultural places. Those places are not only standalone facilities, but they are connected to other infrastructure, which generally should increase the price. This time we decided to look in the neighborhood: we searched for a number of such places in an arbitrarily chosen 1km range. Data was obtained from here.

Both of these external data we visualize in Figure 1.3. Stops are shown on the left and cultural places on the right. Each point indicates the location of the property (marked in green). The blue and red points respectively indicate the location of public transport stops and cultural sites. There are 7549 bus stops and 1214 cultural places in this data.



1.3 Model
Based on the literature we decided to test linear regression models and machine learning models. Below is a list of models that we are considering.

linear regression

fixed effects model

mixed effects model

decision tree

random forest

gradient boosting

xgboost

We collected methods to evaluate the performance of the regression model and decided to use RMSE (root mean square for our models’ assessment).

1.3.1 Linear models
Inspired by literature, we started our analysis by building a white-box linear model. The aim was not to build an ideal model, but rather to get an insight into the relationships in the data and to have a point of reference for more complex models performance and interpretations. Based on economic interpretation, we chose the natural logarithm of price as the dependent variable. The continuous variables characterizing areas were also transformed with natural logarithm. Variables referring to latitude and longitude were omitted since they are unlikely to have a linear effect on price. Instead, zip codes were used to model geographical effects. To avoid collinearity with years since renovation variable, age variable was omitted.


1.3.3 Machine Learning models
Our main goal, as we mentioned before, is to explain the model of choice. Along self-explanatory linear models included as comparison, we considered models including:

decision tree

random forest

gradient boosting

xgboost.



https://pbiecek.github.io/xai_stories/images/02-rmse-train-test.png 



# CONCLUSION

Throughout this analysis I made a machine learning regression project from end-to-end and I learned and obtained several insights about regression models and how they are developed.

With the above analysis we predicted the house prices for every distinguished item from the raw data.

Its dream for every individual to buy a home.

House pricing list serves as a great boon for all the tenants to buy a home. 

This prediction greatly helps house owners to approx. find out the value of their flats/houses.

From investment pov, it helps to find out when exactly one should invest to buy or rent their respective flats/houses.



What is home? My favorite definition is "a safe place," a place where one is free from attack, a place where one experiences secure relationships and affirmation. It's a place where people share and understand each other. Well, sometimes home is a person.
