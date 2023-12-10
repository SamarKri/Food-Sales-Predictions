# Food-Sales-Predictions

## Author 
Samar Krimi

## Business Problem  
A sales prediction for food items sold at various stores to help the retailer to understand the properties of products and outlets that play crucial roles in increasing sales.

## Data Source : sales_predictions_2023.csv
https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view

## Data Dictionary 

![image](https://github.com/SamarKri/sales-predictions/assets/136517111/ba6a53c4-cb25-4ad0-862d-d31d02e3875c)



## Cleaning and Exploring the data 
8523 rows and 12 columns

## Explanatory Data Visualization 

- Histogram to view the distributions of various features 

  ![image](https://github.com/SamarKri/sales-predictions/assets/136517111/e4e74db0-a1e7-40d6-a0a7-35a05b2034a2)

The Item_Outlet_Sales Distribution dramatically decreases with greater prices

- Heatmap of the correlation between features

   ![image](https://github.com/SamarKri/sales-predictions/assets/136517111/876d45d7-c47c-46b2-a10b-a5792cfe7377)

Perfect correlation equal to 1 for : Item_Weight, Item_Visibility , Item_MRP, Outlet_Establishment_Year & Item_Outlet_Sales.
Moderate correlation equal to 0.57 for : Item_MRP with Item_Outlet_Sales
Very low correlation for : The rest of Items and Outlet_Establishment_Year 

- Trends by Bar Chart

  ![image](https://github.com/SamarKri/sales-predictions/assets/136517111/254c3142-f5f6-4fc8-baa0-f5561764d60b)

The Average outlet sales by product category show that : Seafood & Starchy Food are the best-selling they are rich in carbohydrates, nutrients, fiber and vitamins, they are a real source of energy for the body. They are ideal for physical and mental activities. 
In second order are Fruits and Vegetables & Snack Foods which are the most consumed by most people and thirdly Dairy, Canned & Breads. 
Baking Goods & Soft Drinks are the least sold, may be retailer must change their places in the store and I think that they are not recommended for people with certain diseases.

- Trends by Line Graph

![image](https://github.com/SamarKri/sales-predictions/assets/136517111/f2161419-c70f-4c91-a16b-cb310810e1db)

The Item_MR trend seems very fluctuating over the year in which store was established. The the list price of the product increase between 2000 & 2004 years, it falls sharply in 2008 maybe due to the financial crisis. 
Item_Outlet_Sales trend seems almost stable through these years but it falls very sharply in 1998, maybe some sales of certains products are out of stock or a particular store had an incident in this year.

## Preprocessing for Machine Learning 
Preventing data leakage

## Models Evaluation and Results 

### Linear Regression Model :
- This model performs poorly on the training set and testing set regarding R2 metric, this is a case of high bias (underfit). 
- For RMSE metric, our model is incorrect by about 1,115 thousand dollars. 
### Regression Tree Model :
- This model performs perfect on the training data regarding R2 metric. 
- It performs poorly on the testing data, this is a case of high variance (overfitting). 
- For RMSE metric, our model is incorrect by about 1,5 thousand dollars it penalizes more larger errors than Linear model. 
### Regression Tree Model Tuned :
- The best hyperparameter is  for depth=5.
- The R2 testing score become higher, it grows to 0.595 after tuning. 
- The training (0.604) and test (0.595) results have moved closer to each other. 
- The RMSE score is reduced, this model is incorrect by an average of 1,07 thousand dollars. 
By tunning the decision tree model we have reduced overfitting and RMSE metric

## Recommendations for stakeholders
Item_Outlet_Sales can be improved and must be studied according to certain criteria :
- Increasing the amount of best sellers like seafood.
- Focused on fruits and vegetables beneficial to health by making special offers.
- Decrease the amount of unhealthy items like baking Goods & soft Drinks.
- Have always available items sold at various stores to prevent to avoid stock shortage especially in period of health crisis or eventual war.
- Consider selling online and on social networks.
- Changing the packaging and place in the supermarket.

## Future Directions 
  May be change model evaluation such as an improved Random Tree Model and have a better metric results.

## --------------------Project 1 - Revisited------------------------
  
  * For Linear Regression Model, the top 3 most impactful features are:
  
    -Outlet_Type_Supermarket Type3 increased item outlet sales by 2,126.20
    
    -Item_MRP increased item outlet sales by 965.13
    
    -Outlet_Type_Supermarket Type1 increased item outlet sales by 737.28

    ![Coeffs-Linear Regression](https://github.com/SamarKri/Food-Sales-Predictions/assets/136517111/d6680caf-8a41-4d3d-8e5c-c5f45d09bc42)


 * For Decision Tree & Random Forest Models, the top 5 most important features :
 
    -Item_MRP
    
    -Outlet_Type_Grocery_Store

    -Item_Visibility
    
    -Outlet_Type_Supermarket Type3
    
    -Item_Weight

Item_MRP is by far the single most important feature for predicting item outlet sales.

Outlet_Type_Grocery Store is the second most important.

Item_Visibility, Outlet_Type_Supermarket Type3, Item_Weight, are somewhat important.

Everything else is unimportant.

![Importances-Random Forest](https://github.com/SamarKri/Food-Sales-Predictions/assets/136517111/196b4a7a-964e-49ff-ae1f-c9ca32a43f44)
  
