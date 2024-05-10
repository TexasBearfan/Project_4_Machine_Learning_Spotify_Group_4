# Project_4_Machine_Learning_Spotify_Group_4

## Project Overview and Purpose
In this project, we analyzed a dataset of popular songs from Spotify to create and train a machine learning model that can be used to help predict the popularity of a song. We also analyzed various characteristics of these popular songs and created visualizations to show trends of how popular songs with these specific characteristics over time.

## Data Sources
Top 200 Spotify Songs Dataset by Bruno Alarcon from Kaggle
https://www.kaggle.com/datasets/brunoalarcon123/top-200-spotify-songs-dataset

## Process
### Data Cleaning
    * We used Pandas to read in the csv to a jupyter notebook where we deleted unneccessary columns and dropped duplicate values
    * We used pd.to_datetime to change the format of the "Date" column and isolated the data from 5/30/2022 to 5/29/2023 to reduce the dataset so it's more manageable and help identify seasonal trends
    * We then exported the cleaned DataFrame to a csv so it could be used for future analysis
    ![Alt text](image.png)

### Model Creation
    * We used the train_test_split and StandardScaler libraries from sklearn, Pandas, and Tensorflow to create our model
    * After importing our dependencies and cleaned csv file, we dropped additional columns that were not needed for the model
    * We binned the data based on song ranking on the Top 200 chart, in increments of 50
    ![Alt text](image-1.png)

    * We separated the data into labels (y) and features (X)
    * We used pd.get_dummies to create dummy values for our "y", which is the "Popularity" column
    * We then seprated into training and testing datasets, created a StandardScaler instance, then fit and scaled our data
    ![Alt text](image-2.png)

    * We defined, compiled, and trained our model
    ![Alt text](image-4.png)
    ![Alt text](image-3.png)

    * Our first model yielded a fairly low accuracy score of 0.55
    
### Model Optimization/ Testing
    * We used the same data and process as the initial model
    * After creating the StandardScaler, fitting and scaling our data, we attempted numerous different combinations of optimizers, activation functions, loss functions, and number of neurons and hidden layers
    * We were ultimately able to achieve an accuracy score of above 0.75 using this model: 
    ![Alt text](image-5.png)
    ![Alt text](image-6.png)

### Additional Analysis/ Visualizations
    * We wanted to show trends of songs' popularity over time based on various song characteristics
    * Using the cleaned csv file, we converted the "Dated_date" column (which was previously created in the initial cleaning process) and used the below functions to convert to a decimal value and added a new column "Date_value"
    ![Alt text](image-7.png)
    * We then deleted unneccessary columns so we were only including song characteristics and grouped by date
    ![Alt text](image-8.png)
    
    Using this new DataFrame and the MatPlotLib library, we created line graphs showing each the trend of each song characteristic over a year-long period.
    ![Alt text](image-9.png)
    ![Alt text](image-10.png)
    ![Alt text](image-11.png)
    ![Alt text](image-12.png)

## Conclusion
    * We developed a machine learning model trained on a dataset of the Spotify Top 200 Global Songs over one year

    * We processed this data by narrowing down to one year to enhance model accuracy, established four levels of song popularity based on chart rank

    * Created, trained, and optimized a model which demonstrated the potential machine learning in forecasting trends and preferences in the music industry

    * Plans for the future: we can continue improving our model with deeper exploration into seasonal trends. Introducing additional factors, such as geographic or demographic information, would allow for more granular analysis

