# Istanbul House Price Prediction

## 1 - PROBLEM ADDRESSED AND DESCRIPTION OF THE PROBLEM

Istanbul is Turkey's largest city and house prices can be high due to the high population. Therefore, it is important to estimate house prices for people who live in Istanbul or are considering buying a house in Istanbul. However, there are many factors that affect home prices, and the impact of these factors can vary. For example, the opening of a new metro line in a region may increase house prices, while closing a company in an area may lower house prices. In addition, house prices, number of rooms, number of bathrooms, district, population, life index etc. It also depends on many parameters. Therefore, it is difficult to predict house prices in Istanbul and the decision mechanism is uncertain.

In this project, data science methods will be used to predict house prices in Istanbul. First of all, the factors affecting house prices in Istanbul will be determined and then house price prediction models will be created using these factors. Thanks to these models, a categorical house price estimation will be made for people who are considering buying or selling a house in a certain region in Istanbul, thus helping them in the decision-making process about buying a house.

The data set named "Real Estate in ISTANBUL (Emlakjet)" from Kaggle was used as the data set. Dollar rate data is taken from investing.com website.

## 2 - DATA CLEANING AND PRE-PROCESSING STEPS

• First of all, it was checked whether there is any missing data. It appeared not to be.

• Check if there are any repeats. It appeared to be. Duplicate data is deleted with the drop_duplicates method.

• The less number of rooms were categorized as “Other”. After this process, the categories were divided into 5 as 1+1, 2+1, 3+1, 4+1 and Other.

• The numbers 0, 1, 2, 3, 4 are grouped as 0-4 for the age of the building.

• Instead of using the floor where the house is as singular numbers, 6-9, 10-20 etc. grouped accordingly.

• The number of floors of the building should be 1-5, 6-10, 11-15 etc. rather than singular numbers. grouped accordingly.

• There were distortions in the number of bathrooms data. Corrupt data fixed. It's set to be 0, 1, 2, 3, 4, 5, 6+.

• Unknown values in the Credit Eligibility column were classified as “Not Eligible for Credit”.

• Unnecessary columns have been deleted. The reasons are in the picture.

![image](https://user-images.githubusercontent.com/97122999/214565615-dd1c36c9-8bc5-48ef-bf59-257ccbed9dff.png)


• Finally, the grouped data was converted to ML-appropriate format with LabelEncoder from the sklearn.preprocessing library.

## 3 - EXPLANATORY DATA ANALYSIS
### How many listings are there in each county?
![image](https://user-images.githubusercontent.com/97122999/214565960-545ebb33-19fb-434a-8a59-5f4edfe5f856.png)

### Bar Chart for Number of Rooms
![image](https://user-images.githubusercontent.com/97122999/214566258-cc62dd73-3e53-4cb1-8b6b-70b90d77428d.png)

## 4 – INFORMATION ABOUT MACHINE LEARNING ALGORITHMS USED

### Logistic Regression

Logistic regression is a method used for classification in data science. This method examines the relationship between data and estimates the probability that the data will be divided into certain classes (categories). For example, it can be used to predict the probability of a bank customer taking out a loan. This method creates a score according to the characteristics of the customer (age, gender, monthly income, etc.) and the probability of the customer to take out a loan is estimated according to whether this score is above a threshold or not.

Logistic regression works similarly to the linear regression method, but it is a more convenient method for classification than the linear regression method. This method gives a classification probability as an output (for example, the probability of the customer taking a loan is 70%) and the data is classified according to this probability value. For example, if the customer's probability of obtaining a loan is 70% or more, this customer is classified as "to take out a loan", and if it is 70% or less, it is classified as "unable to take out a loan".

### Support Vector Machine

Support Vector Machine (SVM) is a method used for classification and regression in a data science. This method examines the relationship between data and aims to create a line (hyperplane) that best parses the data. This line is created by maximizing the largest margin (margin) between the data and this ensures the best separation of the data. SVM can also be used when the relationship of the data is nonlinear, and this method converts nonlinear relationships to linear relationships using mathematical operations called kernel functions.
SVM can also be used for classification. For example, in a dataset, customers are classified by payment schemes. SVM categorizes data by creating correct that parses data best. This method can also be used when the relationship between data is nonlinear, and this method converts nonlinear relationships to linear relationships using kernel functions. SVM is very widely used among classification methods and generally has high accuracy.

### Random Forest

Random Forest is a method used in data science for both regression (prediction) and classification (dividing data into specific classes). This method creates a set of decision trees and combines the outputs of these decision trees to form predictions. Each decision tree is an algorithm for splitting data using a randomly selected feature set, and Random Forest combines the outputs of these decision trees to create predictions. This method can also be used when the relationship between the data is non-linear, and this method allows the creation of complex models in which many variables are used together.
Random Forest can also be used for classification. For example, in a dataset, customers are classified by payment schemes. Random Forest classifies data by creating decision trees that best parse the data. This method can also be used when the relationship between the data is non-linear, and this
The method allows the creation of complex models in which many variables are used together. This method is widely used among classification methods and generally has a high accuracy.

### Decision Tree Classifier

Decision Tree Classifier is a method used in data science for classification (dividing data into specific classes). This method divides data into classes by creating a decision tree. A decision tree classifies data by creating lines that best parse the data. These lines are created by maximizing the largest margin (margin) between the data and these lines provide the best separation of the data.
The decision tree classifier creates a set of decision rules to classify data. These rules are determined according to the characteristics of the data, and according to the characteristics of the data, it is estimated which class the data belongs to. For example, in a dataset, customers are classified by payment schemes. This method can also be used when the relationship between the data is non-linear, and this method allows the creation of complex models in which many variables are used together.

### K Nearest Neighbor

K Nearest Neighbor (KNN) is a method used in data science for classification (dividing data into specific classes) and regression (prediction). This method classifies data or generates predictions using the coordinates of the data points. This method uses the distance between data points to classify data using the coordinates of the data points. This method classifies data using the distance between data points and generates estimates using the distance between data points.

While KNN is used for classification, it classifies data using the coordinates of data points. This method uses the distance between data points to classify data using the coordinates of the data points. This method classifies data using the distance between data points and generates estimates using the distance between data points. KNN can also be used when the relationship between data is non-linear, and this method allows to create complex models in which many variables are used together.

## 5 - INTERPRETATION OF RESULTS

It is seen that Random Forest Classifier gets the highest scores when tested by training more than one popular classifier algorithm with the real estate dataset.

![image](https://user-images.githubusercontent.com/97122999/214567144-44a41054-e924-4dd2-ae41-499b7e64cf0d.png)

The results in the image above are taken in Turkish Lira. The highest accuracy of Random Forest Classifier is almost the same in every iteration

### Improvement of the Model and Conclusion

The R2 values of the model change as follows when the lowest and highest prices are subtracted from the data set by 10% and the price is based on the dollar exchange rate instead of the Turkish lira. Almost all algorithms have improved in accuracy. The model chosen for Istanbul House Price Estimator was the model trained using RFC with 70% accuracy.

![image](https://user-images.githubusercontent.com/97122999/214567271-7db529a9-d126-4a94-8971-084ddac21611.png)
