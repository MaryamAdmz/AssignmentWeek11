# What drives the price of a car?
In this project, we analyze a dataset from Kaggle containing information on 426k used cars, reduced from the original 3 million for faster processing. Our objective is to identify the key factors that influence a car's price. Based on our findings, we provide recommendations to a used car dealership to better understand what consumers value in a used vehicle.
## Business Understanding
A used car dealership makes money by buying cars at a low price and selling them for more. So, being able to predict a car’s selling price is very important. It’s also important to know which cars people want, so they can sell quickly. Things like the buyer’s age, location, and personal preferences play a big role in what cars are in demand.

## Data Understanding 
This dataset, sourced from Kaggle, includes 426k used cars, a reduced version of the original 3 million, to allow for faster analysis.
### Dataset Overview
- **Size:** 426880  observations with 18 features
- **Data Type and Features:**
  - Numerical Features: price, year, and odometer
  - Categorical Features: region, manufacturer, model, condition, cylinders, fuel, odometer, title_status,    transmission, VIN, drive, size, type, paint_color, and state.
   - Unique Values in Categorical Features:
      - region: 404
      - year: 114
      - manufacturer: 42
      - model: 29649
      - condition: 6
      - cylinders 8
      - fuel: 5
      - odometer: 104870
      - title_status: 6
      - transmission: 3
      - drive: 3
      - size: 4
      - type: 13
      - paint_color: 12
      - state: 51
### Data Cleaning and Data Preparation
 Here is a summary of the missed percentage:
- id    0.0%
- region  0.0%
- price   0.0%
- year    0.28%
- manufacturer  4.1%
- model         1.2%
- condition     40.78%
- cylinders     41.62%
- fuel          0.70%
- odometer      1.03%
- title_status  1.93%
- transmission  0.59%
- VIN           37.72%
- drive         30.58%
- size          71.76%
- type          21.75%
- paint_color   30.50%
- state         0.0%
This dataset is messy, with many missing values and irrelevant columns. For instance, the 'VIN' and 'id' columns can be dropped as they are merely unique identifiers. The 'region' column is redundant since the 'state' column already provides location information. The 'model' column has too many unique values, making it less useful for analysis. Additionally, the 'drive', 'size', and 'paint_color' columns have a high percentage of missing data, 30.6%, 71.8%, and 30.5% respectively, so they can be removed as well. No duplicate records were found in the dataset. With the exception of price and state, all columns contain NaN values. We also removed all rows containing NaN values. The data has now been cleaned by handling all missing values, allowing us to move forward with data exploration and visualizations.
### Defining a Reasonable Price Range Based on IQR
Outliers can be detected using the Interquartile Range (IQR). Using this rule, we calculated the outlier boundaries for the price column:
   - Lower bound: -23885.0
   - Upper bound: 58475.0\
Since negative prices are not realistic, we define a practical safe range for analysis between $5000 and $80,000 for used cars.

outlier boundaries for the odometer column:
   - Lower bound: -106053.75
   - Upper bound:  277300.25\
Since negative or extremely high odometer readings are not realistic, we define a practical range for analysis between 5000 miles and above for a used car.
After all the data manipulations discussed above, we reviewed the correlation matrix for the final dataset. Among the categorical variables created, the strongest correlation with price was observed for fuel_diesel. Overall, most correlations with price were negative. The only attributes showing positive correlations were year, condition_like_new, fuel_diesel, size_full-size, and drive_4wd. Although these correlations are positive, none are particularly strong—the highest, for fuel_diesel, remained below 0.85. Therefore, no variables were removed solely based on these correlation results.
#######






## Modeling
With the final cleaned dataset prepared, we proceeded to build several regression models using price as the target variable. We experimented following regression algorithms and explored various parameter settings to optimize model performance. To ensure the robustness of our findings, we applied cross-validation techniques during model training and evaluation.

 - Model 1: Simple Linear Regression using the full set of features using the final dataset
 - Model 2: Regression Model using a selected number of features only
 - Model 3: The application will be developed using the features that show stronger correlations with price in the dataset filtered to include records where odometer > 5,000 and price > 5,000. The selected features are odometer, year, fuel_diesel, drive_4wd, and size_full-size.
 - Model 4: The application will be developed using the features that show stronger correlations with price in the filtered dataset where odometer > 5,000, price > 5,000, and year > 1990. These selected features include odometer, year, fuel_diesel, drive_4wd, and size_full-size.
 


## Evaluation

## Deployment
