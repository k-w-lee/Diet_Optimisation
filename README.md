# Diet_Optimisation

### Objective
To optimize diet with minimum cost while satisfying daily nutrition intake targets and constraints.

### Introduction and Overview:
During MCO, it is common to notice citizens with rising of overweight issue and a preventive healthcare of obesity
plan is demanding. Thus, diet optimisation system with minimum ingredient cost while satisfying constraints of
nutrition goal is proposed to the health organisation of Gleneagles Hospital Penang to target new segment of
customers by the new value-added service. The diet subscription plan allows the hospital customers to choose either
to dine in or get their food delivered. Thus, customers can enjoy hassle-free weight adjustment meal, meanwhile the
hospital can develop new profit source, new segment of customers while minimise ingredient cost.

### Problem Statement Summary
1. Overweight Citizen is growing during MCO.
2. Difficult to fulfill all daily needs nutrition
3. Physical restriction for a preventive plan from obesity

### Datasets
There are two (2) datasets we are going to use; the first dataset is  [Food Nutrition Information](https://data.world/adamhelsinger/food-nutrition-information). The dataset included
sixty-one (61) instances about nutritional information for raw edible fruits, raw edible vegetables, and seafood (cooked
by moist or dry heat with no added ingredients). 

The second dataset is  ["Subjects with Overweight Issue"](https://www.kaggle.com/ankurbajaj9/obesity-levels?select=ObesityDataSet_raw_and_data_sinthetic.csv) dataset comprised of real data of overweight subjects. The subjects are setting
off for weight reduction program to identify the combinations of diet that able to satisfy all nutrients goals’ constraints
with minimum cost.

### Techniques Involved

#### Dataset Pre-Processing
The dataset will be pre-processed to fit into the LP Model. The original dataset of “Food Nutrition Information” has no
"Price" column. The solution is to manually match the Food with price list in [Tesco Online Shop](https://eshop.tesco.com.my/groceries/en-GB/shop/fresh-food/all). On the other hand,
the daily nutrition goals are determined by setting up weight goal by participant in fitness app of [Myfitnesspal](https://www.myfitnesspal.com/food/diary/). The
sample data of Daily Nutrition Goal for a participant is shown in this [link](https://drive.google.com/file/d/10kAK-6gbpdNxEKoq0Jdx6nuG0fYXULdN/view?usp=sharing).
#### Linear Programming (LP) Model
Excel Solver will be used as the platform to build a LP model to calculate the optimum cost of diet to determine the
best proportion of diet using least cost. Moreover, Simplex Method will be used as the solving method for the LP
model. Safety intake amount constraints are obtained from publication [“Recommended Nutrients Intakes for
Malaysia”](http://nutrition.moh.gov.my/wp-content/uploads/2017/05/FA-Buku-RNI.pdf) by Ministry of Health Malaysia. The constraints of the model are proposed as follow:

    • Daily Safety Intake Amount >= Daily Proportion of Nutrition Intake >= Daily Intake Sent by Fitness App
    
    • Total Daily Calories <= Daily Calories Intake Goal


The decision variables here is to find the optimum combinations of diet, N, that can minimize the food cost for a
month, Z (Minimum). The proposed formula of Z (Minimum) is as follow:


<p align="center">
    Z (Minimum) = Sum Product (N, Cost)
</p>
Thus, by using this linear programming model, the hospital can find the right proportion of ingredients with minimum
cost to serve their subscribed customers.
