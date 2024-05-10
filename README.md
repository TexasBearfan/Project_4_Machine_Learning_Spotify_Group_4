# Project_4_Machine_Learning_Spotify_Group_4

## Project Overview and Purpose
In this project, we analyzed a dataset of popular songs from Spotify to create and train a machine learning model that can be used to help predict the popularity of a song. We also analyzed various characteristics of these popular songs and created visualizations to show trends of how popular songs with these specific characteristics over time.

## Data Sources
Top 200 Spotify Songs Dataset by Bruno Alarcon from Kaggle - this dataset includes the top 200 songs on Spotify from 1/1/2017 through 5/29/2023, and has over 650,000 records
https://www.kaggle.com/datasets/brunoalarcon123/top-200-spotify-songs-dataset

## Process
### Data Cleaning
* We used Pandas to read in the csv to a jupyter notebook where we deleted unneccessary columns and dropped duplicate values
* We used pd.to_datetime to change the format of the "Date" column and isolated the data from 5/30/2022 to 5/29/2023 to reduce the dataset so it's more manageable and help identify seasonal trends
* We then exported the cleaned DataFrame to a csv so it could be used for future analysis - the cleaned CSV has over 100,000 records.
  
![image](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/be4c5ee4-2afc-4579-ad17-03226b68c049)

### Model Creation
* We used the train_test_split and StandardScaler libraries from sklearn, Pandas, and Tensorflow to create our model
* After importing our dependencies and cleaned csv file, we dropped additional columns that were not needed for the model
* We binned the data based on song ranking on the Top 200 chart, in increments of 50
  
![image-1](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/044a910c-b1a9-4b90-83ff-d615c958f581)

* We separated the data into labels (y) and features (X)
* We used pd.get_dummies to create dummy values for our "y", which is the "Popularity" column
* We then seprated into training and testing datasets, created a StandardScaler instance, then fit and scaled our data

![image-2](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/34dcb180-e21f-48ea-b8ef-1a0a06f37e2a)

* We defined, compiled, and trained our model
  
![image-4](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/012298e9-94e6-47e1-b1ef-029c56da14b2)

![image-3](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/e7fd6030-7880-4005-b79a-7451ab6a7785)

* Our first model yielded a low accuracy score of 0.29
    
### Model Optimization/ Testing
* We used the same data and process as the initial model
* After creating the StandardScaler, fitting and scaling our data, we attempted numerous different combinations of optimizers, activation functions, loss functions, and number of neurons and hidden layers
* We were ultimately able to achieve an accuracy score of above 0.75 using this model: 

![image-5](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/caf34c31-2ead-48a0-ab98-db81a31a0b08)
![image-6](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/ca8bf6c6-f1d3-4794-999e-a5bf712b196b)

### Additional Analysis/ Visualizations
* We wanted to show trends of songs' popularity over time based on various song characteristics
* Using the cleaned csv file, we converted the "Dated_date" column (which was previously created in the initial cleaning process) and used the below functions to convert to a decimal value and added a new column "Date_value"

![image-7](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/9d247668-95e8-462b-a1a4-32dccabe2d58)

* We then deleted unneccessary columns so we were only including song characteristics and grouped by date

![image-8](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/9cbace72-43fa-4937-ab36-0aa6775e9d11)
    
* Using this new DataFrame and the MatPlotLib library, we created line graphs showing each the trend of each song characteristic over a year-long period.

![image-9](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/521124ae-0c36-4615-a301-197542f5a56c)
![image-10](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/3661244b-e2b7-4294-869c-de53d8c29279)
![image-11](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/fbc34f7f-42da-4c6f-8d9a-e5bf4e1a0769)
![image-12](https://github.com/TexasBearfan/Project_4_Machine_Learning_Spotify_Group_4/assets/147567143/966ceae5-3c70-46e9-ab16-4020eac77e3e)


## Conclusion
* We developed a machine learning model trained on a dataset of the Spotify Top 200 Global Songs over one year
* We processed this data by narrowing down to one year to enhance model accuracy, established four levels of song popularity based on chart rank
* We created, trained, and optimized a model which demonstrated the potential machine learning in forecasting trends and preferences in the music industry
* Next steps: we can continue improving our model with deeper exploration into seasonal trends. We can introduce additional factors, such as geographic or demographic information, would allow for more granular analysis

