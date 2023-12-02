# What Drives the Price of a Car?
## Background
This is a practical application assignment as part of a 6-month Berkley Engineering | Hass Artificial Intelligence and Machine Learning Professional Certificate program.

## Business Understanding
We are tasked with exploring and analyzing records of car sales transactions to identify key drivers for used car prices. The goals are to understand what factors make a car more or less expensive and to provide clear recommendations to the client, a used car dealership, as to what consumers value in a used car.

## Data Understanding
This dataset is a subset  of a 3-million records source from Kaggle. The size is reduced to 426K car sales information to accommodate the  processing power of a personal or laptop computer. It does not come with data descriptions, and the dataset's source is no longer traceable. Here is my understanding of the dataset. All transactions are assumed to have taken place in 2022.

* id: Unique identifier of a car sales transaction
* region: City or metropolitan area where the transaction occurred
* price: Price sold
* year:  The car's model year. From 1900 to 2022
* manufacturer:  Manufacturer/brand of the car
* model: Model of the car. Some descriptions are also provided in this column. e.g. 'ford f350 4wd truck'
* condition: Possible values include, 'new,' 'excellent,' 'fair,' and 'salvage.'
* cylinders: Number of cylinders in textual form. e.g. '6 cylinders'
* fuel: Categorical values of 'diesel,' 'gas,' 'electric,' 'hybrid,' or 'other'
* odometer: Odometer reading (Presumably in miles)
* title_status:  Categorical values of 'clean,' 'lien,' 'parts only,' etc.
* transmission:  'automatic,' 'manual,' or 'other'
* VIN: Vehicle Identification Number
* drive: '4wd', 'fwd', or 'rwd', stands for 4-wheel-drive, front-wheel-drive, and rear-wheel-drive, respectively
* size: 'full-size,' 'mid-size,' 'compact', or 'sub-compact'
* type: 'sedan. 'SUV', 'pick up', 'truck', 'bus', etc.
* paint:_color: body color
* state: U.S. state where the sales transaction occurred

## Data Quality
During my initial data exploration, three-quarters of the 426k records had to be scrapped due to duplicates and data anomalies. For example, 40% of the transactions had duplicated Vehicle Identification Numbers, a 2005 Toyota Tundra was priced at 3.7 billion, and cars classified as in 'new' condition had an average age of 6.5 years and 54k odometer readings. Great efforts have been taken to remove apparent and not-so-apparent data anomalies before real analysis begins.

## Classic, Vintage, and Antique Cars
The prices of classic, vintage, and antique cars are known to depend on the scarcity of these cars. However, since the dataset does not provide that information, they are excluded from this analysis.

## Car Sales Price by Car Age
(plot)

## Average Sale Price by Car Manufacturers
(plot)

## Average Sale Price by Car Types
(plot)

## Average Sale Price by Fuel Types
(plot)

## Average Sale Price by Drive Types

## What Drives the Price of a Used Car?

### Key Insights
The dataset contains 16 attributes of a car sales transaction, including the features and specs of the car and where the transaction occurred. All attributes affect the price of a used car to some extent. Six factors were identified as key influencers on the sale price - the Ferrari prestige, diesel engine premium, front-wheel-drive disadvantage, cylinder horsepower, and age/mileage wear-and-tear. 

### Quantitative Analysis
Several linear regression models with LASSO regularization were built for the quantitative analysis after painstaking data cleansing. These factors were identified as key influencers on the price of used cars. In order of importance: 
1. The Ferrari Brand: Ferrari cars were sold at prices significantly higher. On average, a Ferrari is priced $125,000 higher than other brands, with all other car features and conditions being identical.
2. Diesel engine premium: Cars equipped with diesel engines tend to have a higher value, approximately $13,000 more than cars without this feature.
3. Drive Type: Front-wheel drive cars have a slightly lower average price than 4-wheel or rear-wheel drive counterparts. When other features remain constant, a front-wheel-drive car was sold for $4,100 less.
4. Cylinder's horsepower: Each additional cylinder in a car contributes approximately $2,450 to the car's price when other factors remain constant. More cylinders usually translate to a higher horsepower and make a car more valuable. Since the dataset does not come with the horsepower specs of cars, the number of cylinders becomes a good approximator.
5. Age of the Car: On average, the price of a car reduces by $1,116 for each year it ages, assuming other features remain constant.
6. Odometer Reading: The mileage or odometer reading also plays a role in price determination. The car's value decreases by $0.06 for each mile driven, much less than I expected. It's likely some un-caught data anomalies have yet to be discovered.

### Other Factors
Other than the factors identified above, the car's condition, title status, and other features are believed to affect a car's price. However, due to quality issues and anomalies in the dataset, they are not used to make inferences or forecasts. For example, based on the dataset, the average age of 'new' cars is 6.5 years old, with 54k odometer readings. Those data anomalies had to be removed, and the conditions of vehicles could not be trusted and had to be ignored. Some unmeasured factors, such as horsepower and scarcity of vintage and antique cars, are not part of the dataset.
