# Flight-Price-Prediction
A Regression Project that predicts flight prices 

Flight prices change all the time and everyone likes a good bargain! 

### Datasets

This project consists of 2 datasets - the train and test. 

Both Dataset have the following information:

1. Airline - name of airline

2. Date of Journey -date in dd/mm/yyyy

3. Source - Departure City

4. Destination - End City

5. Route - all the cities the flight goes through

6. Dep_time - Departure time

7. Arrival_time - Arrival Time

8. Duration - How long the flight is 

9. Total_stops - Is the flight non-stop or does it have any stops

10. Additional_info - Information like in-flight meal, layovers, baggage, etc is included in this column.

<i>Price</i> is the predictor (y) variable, it is included in the train dataset and must be predicted for test 


### Objectives 

The objective of this project is to predict the price of a flight when a set of relevant flight details are provided. This kind of model can be used to predict the fair price of a flight. The flight details has information related to flight timings, source and destination details, route details, stops in between etc.

The dataset consists of about four months of information about various flights and their respective prices. You are to analyze the data and provide the below:
1. Identify the Independent variables which are significant

2. Build predictive models to predict flight prices. Split the data into training and test sets. Build supervised models on training data and test it on the test. Use RMSE as the metric for model evaluation.

3. Use the best model to predict flight prices for which we do not have the flight prices. This is the second dataset attached. (It has 2500 observations for which flight prices have to be predicted)


### EDA Conclusions

1. The Test & Train Datasets mirror each other, which means any models we build will be appropriate.

2. The most common flight path is from Delhi to Cochin. The least common flight path is from Chennai to Cochin. 

3. One-stop flights are the most commonly booked flights. 

4. Jet Airway Economy class is the most popular flight type. The most expensive flight type is Jet Airways Business Class. 

5. April is the cheapest month to fly. Friday has the most flight bookings. 

### Feature Selection Notes

After Feature selection using SelectKBest - ChiSquared and Extra Tree Regression method, SelectKBest shows that all columns are equally important. Based on the SelectKBest plot, out of 31 columns, only "Journey Month" is an unimportant factor that can be ignored. So a model that says 30 columns out of 31 are important is not to be used. 

Extra Tree Regression method shows better results. The plot shows that 15 columns or features are the most important. There is a sharp decline between the importance factor of the first 15 features and the rest 16. 

Based on Extra Tree Regression Method, the most important features: 

1. Whether a flight is non-stop 
2. The Date of the journey
3. Jet Airways Economy Class
4. Jet Airways Business Class
5. The Month of the journey 
6. How many hours of journey
7. Indigo Economy Class
8. The Arrival Hour 
9. The departure Hour
10. Flight has 2-stops between departure and final arrival airports
11. The Departure Minute
12. The Arrival Minute
13. Destination Airport is Delhi
14. How many minutes of Journey
15. Multiple Carrier Airlines

This shows that the factors that people take into consideration while booking a flight are:

<i>Whether it is a Non-Stop or Two-Stop flight 

The Date and Month of trip, 
 
Departure & Arrival times, 

Flight Duration, 

Jet Airways (Economy & Business), Indigo Economy are both highly sought

Delhi Destination</i>


### Summary of Model Evaluation Stats:

Test	RMSE	R-Squared
KNN	2241.51	73.89%
Ridge	2823.84	58.57%
Lasso	2822.12	58.62%
Decision Tree	2582.46	65.35%
Hyper-Tuned Random Forest	1794.94	83.26%
Hyper-Tuned XGBoost	1927.71	80.69%
Stacked Regression 	2085.37	77.40%

Ran the Hyper Tuned Random Forest & XGBoost models to predict the prices. 
