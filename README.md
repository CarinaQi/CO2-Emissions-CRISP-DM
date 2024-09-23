# CO2 Emissions Data Mining using CRISP-DM
## Source of Data
In this iteration, the dataset I used is retrieved from https://www.kaggle.com/datasets/anshtanwar/global-data-on-sustainable-energy
The dataset appears to compile information related to sustainable energy from various sources worldwide according to the dataset provenance, including World Bank, International Energy Agency, and ourworldindata organization. Also, some of data are taken from other Kaggle datasets. However, after verifying data quality, I found that there are lots of missing values in the year 2020, especially the CO_2 emissions value which is our target attribute. Therefore, I will merge a supplementary dataset from https://ourworldindata.org/co2-and-greenhouse-gas-emissions#explore-data-on-co2-and-greenhouse-gas-emissions to fill up the missing value in the year 2020.


## Screenshot of Dataset Information
  There are 3,649 records and 21 attributes to process in this database, spanning from 2000 to 2020 and covering 176 countries, the dataset offers a robust foundation for  conducting meaningful analyses of CO_2 emissions patterns and trends.

<img width="652" alt="Screenshot 2024-09-23 at 3 55 09 PM" src="https://github.com/user-attachments/assets/6f3f789e-1d1a-4397-8f30-f61beb4d6af3">


## Screenshot of Data Type
The datasets encompasses a variety of value types, including string (1), integer (3), float (17). Float values represent quantitative data such as electricity from sources, CO_2 emissions value, and GDP growth. Countries which named Entity attribute is in string value. Year, density, land area are in integer value.

<img width="452" alt="image" src="https://github.com/user-attachments/assets/85d675e3-f648-4e40-ace0-94b4fc66762a">

## Data Distribution
We can find that most countries produce less than 1 million CO_2 emissions.

<img width="452" alt="image" src="https://github.com/user-attachments/assets/aa3a9d0f-bbaa-49ff-8a6b-a6d753f974e0">

The top 20 countries ranked by mean CO_2 emissions, we notice that only Japan, India, the United States, and China exceed the 1 million CO_2 emissions. Among these, the United States and China stand out with significantly high CO_2 emissions values, highlighting their substantial impact on global emissions.
<img width="452" alt="image" src="https://github.com/user-attachments/assets/a1fee784-1044-4477-bde0-c4c68f6e13bb">

## Attributes importance rank (correlation)
Ranking the attributes importance by their absolute correlation with CO_2 emissions

<img width="659" alt="Screenshot 2024-09-23 at 4 00 17 PM" src="https://github.com/user-attachments/assets/d05ac9ec-8ec1-4134-94fd-1a088b17d0ca">

## Data Mining
### Train-Test Data split
Split the data into a training set (70%) and a separate test set (30%). Train the model on the training set and evaluate its performance on the test set. If the model performs significantly better on the training set than on the test set, it may be overfitting.

<img width="452" alt="image" src="https://github.com/user-attachments/assets/2ec67750-8c93-41ca-94a3-dc2b9f8a7cfd">

### Linear Regression

<img width="452" alt="image" src="https://github.com/user-attachments/assets/27dd0741-39f7-42aa-b55b-31bb215824c1">
<img width="452" alt="image" src="https://github.com/user-attachments/assets/928bf074-fbeb-4089-bfb1-a5b50deb439c">


### Decision Tree
<img width="453" alt="image" src="https://github.com/user-attachments/assets/7d78e384-05ad-4f4b-82ca-1cdb39b74139">

## Visualization
### Heatmap of coefficients of between 〖CO〗_2 emissions and other factors
the colours in the heatmap represent the magnitude and direction of the coefficients. Typically, a colour gradient ranging from cool colours (e.g., blue) to warm colours (e.g., red) is used to indicate negative and positive coefficients, respectively.

Therefore, we focus on CO_2 emissions column, and we can find that electricity from fossil fuels is dark red, which means significant positive linear relationship with CO_2 emissions. Electricity from renewables and Annual_GDP are orange, which means strong positive linear relationship with CO_2 emissions. Electricity from nuclear and land area are light blue, which means weak-moderate relationship with CO_2 emissions.

<img width="452" alt="image" src="https://github.com/user-attachments/assets/56d0144a-457a-4f6c-af6f-7b02ca21439a">

### Linear Regression plot (actual 〖CO〗_2 emissions: scatter vs the predicted values: line)
The line indicates the predict CO_2 emissions model we build. The scatter indicates the actual CO_2 emissions data. The figure shows that the model we build mostly fit well with actual data, except the top right two spots, which are China and United States. And most countries are on bottom left, which are produce less than 1 million CO_2 emissions.
<img width="452" alt="image" src="https://github.com/user-attachments/assets/a4aefc59-f765-40ba-a1ce-b68217d95d7a">


## Model Accuracy
### Linear regression
linear regression model has been evaluated using test set to avoid overfitting. 98.93% accuracy (R2) indicates a high degree of goodness-of-fit between the linear regression model and the actual data. 
The RMSE value represents the average magnitude of error in the predictions of the model. Lower values of RMSE indicate better fit. In this case, RMSE is quite high (86150), suggesting that the average error in CO₂ emissions predictions is quite large.  However, given the large scale of CO₂ emissions, this error needs to be evaluated in context.
<img width="452" alt="image" src="https://github.com/user-attachments/assets/f0fb7457-94cb-4fe2-947b-7bc5b75854e8">
