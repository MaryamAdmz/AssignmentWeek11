# What drives the price of a car?
In this project, we analyze a dataset from Kaggle containing information on 426k used cars, reduced from the original 3 million for faster processing. Our objective is to identify the key factors that influence a car's price. Based on our findings, we provide recommendations to a used car dealership to better understand what consumers value in a used vehicle.
## Business Understanding
A used car dealership makes money by buying cars at a low price and selling them for more. So, being able to predict a car’s selling price is very important. It’s also important to know which cars people want, so they can sell quickly. Things like the buyer’s age, location, and personal preferences play a big role in what cars are in demand.

## Data Understanding and Data Preparation
This dataset, sourced from Kaggle, includes 426k used cars, a reduced version of the original 3 million, to allow for faster analysis.
### Dataset Overview:
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
      - state: 51\
## Data Cleaning
This dataset is messy, with many missing values and irrelevant columns. For example, VIN and id can be dropped since they are just unique identifiers. The region column is also unnecessary because we already have the state column. Additionally, the model column has too many unique values, making it less useful for analysis, so it can be removed as well. No duplicates were detected.\
With the exception of price and state, all columns contain NaN values. Here is a summary of the missed percentage and the action necessary:
- year
  - missed percentage: %0.28,
  - Action: Filling with the most common value
- manufacturer  %4.13, Action: Filling with "Other" as this is a categorical column
- condition  %40.78, Action: Filling with the most common value
- cylinders  %41.62 Action: Remove the word cylinders, replace others and missed values by filling with the most common value
- fuel %0.71 Action: Filling with "Other" as this is a categorical column
- odometer %1.03 Filling with odometer mean
- title_status %1.93 Filling with the most common value
- transmission %0.60 Filling with "Other" as this is a categorical column
- drive %30.  53 Action: Delete this column because missed records percentage
- size  %71.77 Action: Delete this column because missed records percentage
- type  %21.75 Action: Filling with "Other" as this is a categorical column
- paint_color %30.50 Action: Delete this column because missed records percentage


## Modeling

## Evaluation

## Deployment
