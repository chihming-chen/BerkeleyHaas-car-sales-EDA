# What Drives the Price of a Car?
## Background
This is a practical application assignment as part of a 6-month Berkley Engineering | Hass Artificial Intelligence and Machine Learning Professional Certificate program.

## Business Understanding
We are tasked with exploring and analyzing records of car sales transactions to identify key drivers for used car prices. The goals are to understand what factors make a car more or less expensive and to provide clear recommendations to the client, a used car dealership, as to what consumers value in a used car.

## Data Understanding
This subset includes 426K car sales information to ensure processing speed on a personal or laptop computer. However, it does not come with data descriptions, and the dataset's source is no longer traceable. Here is my understanding of the dataset:

* id: Unique identifier of a car sales transaction
* region: City or metropolitan area where the transaction occurred
* price: Price sold
* year:  The car's model year. From 1900 to 2022
* manufacturer:  Manufacturer/brand of the car
* model: Model of the car. Some descriptions are also provided in this column. e.g. 'ford f350 4wd truck'
* condition: Possible values include, 'new,' 'excellent,' 'fair,' 'salvage'
* cylinders: Number of cylinders in textual form. e.g. '6 cylinders'
* fuel: Categorical values of 'diesel,' 'gas,' 'electric,' 'hybrid,' or 'other'
* odometer: Odometer reading
* title_status:   Categorical values of 'clean,' 'lien,' 'parts only,' etc.
* transmission:  'automatic,' 'manual,' or 'other'
* VIN: Vehicle Identification Number
* drive: '4wd', 'fwd', 'rwd' stand for 4-wheel-drive, front-wheel-drive, and rear-wheel-drive, respectively
* size: 'full-size,' 'mid-size,' 'compact,' 'sub-compact'
* type: 'sedan. 'SUV,' 'pick up', 'truck', 'bus,' etc.
* paint:_color: body color
* state: U.S. state where the sales transaction occurred \n 
</pre>

## Data Source and Its Quality
The data is sourced from Kaggle, a popular website for data scientists. The original dataset contains more than 3 million car sales transactions, but it is reduced to 426K transactions that occurred in 2022 in the United States. During initial data exploration, three-quarters of the 426k records had to be scrapped due to duplicates and data anomalies. For example, 40% of the transactions have duplicated Vehicle Identification Numbers, and cars classified as in 'new' condition had an average age of 6.5 years and 54k odometer readings. Great efforts have been taken to remove apparent and not-so-obvious data anomalies before real analysis begins.

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
* Brand Impact: Ferraris significantly increases a car's price due to their brand, high horsepower, and exclusivity.
* Diesel Engine Premium: Cars with diesel engines tend to have a higher resale value.
* Drive Type Influence: Front-wheel drive cars are more common but slightly less expensive than other drive types.
* Cylinder Contribution: Each additional cylinder in an engine adds horsepower and value to the car.
* Age and Mileage Impact: Older cars with higher mileage generally have reduced prices due to wear and tear. 

### Quantitative Analysis
Several linear regression models with LASSO regularization were built for the quantitative analysis after painstaking data cleansing. Six factors were identified as key influencers on the price of used cars. Here are the six factors below in order of their importance:
1. The Ferrari Brand: Ferrari cars were sold at prices significantly higher. On average, a Ferrari is priced $130,885 higher than other brands, with all other car features being identical.
2. Diesel Engine: Cars equipped with diesel engines tend to have a higher value, approximately $2,454 more than cars without this feature.
3. Drive Type: While common, Front-wheel drive cars have a slightly lower average price than 4-wheel or rear-wheel drive counterparts. On average, a front-wheel-drive car was sold for $1,941 less.
4. Number of Cylinders: Each additional cylinder in a car contributes approximately $2,385 to the car's price when other factors remain constant. We all know that the number of cylinders is highly correlated to horsepower. More cylinders usually translate to a higher horsepower and make a car more valuable. Since the dataset does not come with the horsepower specs of cars, the number of cylinders becomes a good approximator.
5. Age of the Car: On average, the price of a car reduces by $1,416 for each year it ages, assuming other features remain constant.
6. Odometer Reading: The mileage or odometer reading also plays a role in price determination. The car's value decreases by $0.01 for each mile driven, much less than I expected. It's likely some un-caught data anomalies have yet to be discovered.

### Other Factors
Other than the above, the car's condition, title status, and other features are believed to affect a car's price. However, due to quality issues and anomalies in the dataset, they are not used to make inferences or predictions. For example, based on the dataset, the average age of 'new' cars is 6.5 years old, with 54k odometer readings. Those data anomalies had to be removed, and the conditions of vehicles could not be trusted and had to be ignored. There are also some unmeasured factors, such as horsepower, and scarcity of vintage and antique cars, that are not part of the dataset.

