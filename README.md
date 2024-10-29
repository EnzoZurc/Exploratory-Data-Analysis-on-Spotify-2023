##### Christian Enzo B. Cruz
##### 2ECE-D
<p align="center">
    Exploratory Data Analysis on Spotify 2023 Dataset
</p>
</br>
&nbsp;This ReadMe file will serve as a full documentation on my exploratory data analysis on the given data set. </br></br>

### Overview of Data Set
#### * &nbsp;&nbsp;How many rows and columns does the dataset contain? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After loading the downloaded CSV file (I had trouble loading the file so I had to ask ChatGPT for corrections and alternative way to load the file.), I reviewed the dataset's structure, revealing a total of 953 rows and 24 columns. This can be seen on the images below.</br>
![image](https://github.com/user-attachments/assets/004c3e36-0056-4baf-b644-6de938c5bacc)</br>
![image](https://github.com/user-attachments/assets/ee3691ac-4a33-4742-bba2-79c937148a17)</br></br>


#### * &nbsp;&nbsp;What are the data types of each column? Are there any missing values? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To examine the data types of each column and identify any missing values, the syntax .info can be used. After running this, we see missing values in the columns in_shazam_charts and key, with 50 missing entries in in_shazam_charts and 95 in key.</br>
![image](https://github.com/user-attachments/assets/4bd7c796-c108-4607-9c10-ef46be83267e)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To further explore this, I consulted ChatGPT for a more effective way to visualize the information. Seen on the image below.</br>
![image](https://github.com/user-attachments/assets/3c02a9c5-3a1e-41ec-82c7-9612aa323257)</br></br></br>


###  Basic Descriptive Statistics
#### * &nbsp;&nbsp;What are the mean, median, and standard deviation of the streams column? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The first problem I encountered was that the data type of the column 'streams' was OBJECT, thus I had to convert it first to numerical/int using the following syntax:</br>
![image](https://github.com/user-attachments/assets/c7cc932c-d56d-4ed9-af35-d01bbabfb623)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After converting I can now easily get the mean median and standard deviation using the syntaxes below.</br>
![image](https://github.com/user-attachments/assets/ebcba88d-4cad-46d9-a5b6-93dd4d2f6dc7)</br></br>

#### * &nbsp;&nbsp;What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers? </br>
