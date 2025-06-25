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
This dataset is messy, with many missing values and irrelevant columns. For instance, the 'VIN' and 'id' columns can be dropped as they are merely unique identifiers. The 'region' column is redundant since the 'state' column already provides location information. The 'model' column has too many unique values, making it less useful for analysis. Additionally, the 'drive', 'size', and 'paint_color' columns have a high percentage of missing data, 30.6%, 71.8%, and 30.5% respectively, so they can be removed as well. No duplicate records were found in the dataset.
With the exception of price and state, all columns contain NaN values. Here is a summary of the missed percentage and the action necessary:
- year
  - missed percentage: %0.28
  - Action: Filling with the most common value
- manufacturer
  - missed percentage: %4.13
  - Action: Filling with 'other' as this is a categorical column
- condition
  -  missed percentage: %40.78
  -  Action: Filling with the most common value
- cylinders
  -  missed percentage: %41.62
  -  Action: Remove the word cylinders, replace others and missing values by filling with the most common value
- fuel
  - missed percentage:%0.71
  - Action: Filling with 'other' as this is a categorical column
- odometer
  - missed percentage: %1.03
  - Action: Filling with the odometer mean
- title_status
  - missed percentage: %1.93
  - Action: Filling with the most common value
- transmission
  - missed percentage:%0.60
  - Action: Filling with 'other' as this is a categorical column
- type
  - missed percentage: %21.75
  - Action: Filling with 'other' as this is a categorical column\
The data has now been cleaned by handling all missing values, allowing us to move forward with data exploration and visualizations.
### Defining a Reasonable Price Range Based on IQR
Outliers can be detected using the Interquartile Range (IQR). Using this rule, we calculated the outlier boundaries for the price column:
   - Lower bound: -23885.0
   - Upper bound: 58475.0
Since negative prices are not realistic, we define a practical safe range for analysis between 100 and 80,000.

## Modeling

## Evaluation

## Deployment
