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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;First to find the **trends** of the released_year and artist_count I used histogram plots to easily see them, which is shown on the image below. </br>
![image](https://github.com/user-attachments/assets/1aa49549-7605-47bf-97e3-0f91cd1b638b)</br>
![image](https://github.com/user-attachments/assets/12edba1c-fb6f-45cd-a30a-2429101e5189)</br>
![image](https://github.com/user-attachments/assets/cd3b6bef-6c9f-4f60-a343-ce35ce99f086)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After viewing the plots I concluded that the dataset is heavily skewed towards recent music releases, with the majority of songs concentrated around and after the year 2020. This sharp increase in frequency near the end of the timeline indicates a strong emphasis on contemporary music, suggesting that the dataset may be designed to reflect current trends in streaming. In contrast, songs released before the year 2000 are sparsely represented, with almost negligible counts for releases prior to the 1980s. This shows a significant recency bias in the data, highlighting a potential lack of representation for older music.</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As fot the histogram of the artist_count, it shows that most songs in the dataset feature a single artist, with a noticeable drop in frequency for songs with two artists. While two-artist collaborations are still somewhat common, songs with three or more artists become increasingly rare. Overall, the data is heavily skewed toward solo and small-group performances, with larger collaborations being uncommon. </br></br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To identify the **outliers**, I used box plots, which made it easier to spot them visually. Seen on the image below.</br>
![image](https://github.com/user-attachments/assets/0c067bde-506a-48b2-8ef5-fd42935e53ff)</br>
![image](https://github.com/user-attachments/assets/54dead4b-78b8-4f05-ad98-54b265657a9e)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Reviewing both plots, The box plot for **released_year** shows that most songs in the dataset were released around the most recent years, as indicated by the concentration of values near the end of the timeline. The outliers, represented as individual dots extending to the left, are songs released in earlier years (e.g., before 1980). These outliers indicate that there are a few older songs in the dataset, which are far from the main cluster of more recent releases.</br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As for the box plot for **artist_count** indicates that most songs have one or two artists, as shown by the interquartile range covering these values. The outliers here are songs with a higher number of artists, specifically four to eight artists. These outliers reflect less common instances where a song has many contributing artists, which deviate significantly from the typical one or two-artist scenario.</br></br></br>


###  Top Performers
#### * &nbsp;&nbsp;Which track has the highest number of streams? Display the top 5 most streamed tracks. </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To find the top 5 streamed trackes we'll have to sort the data set based on their stream values using the following code.</br>
![image](https://github.com/user-attachments/assets/9d412dc5-4820-4166-b8ec-4f439e79d4b6)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Based image above we can see that the top 5 streamed tracks are Blinding Lights by the Weeknd, Shape of You by Ed Sheeran, Someone You Loved by Lewis Capaldi, Dance Monkey by Tones and I, and Sunflower - Spider-Man: Into the Spider-Verse by Post Malone and Swae Lee respectively.</br></br>

#### * &nbsp;&nbsp;Who are the top 5 most frequent artists based on the number of tracks in the dataset? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To find this we have to count how many times the artist appears in the data set, then we have to sort it based on the first 5 entries that is most frequent. The code is shown on the image below.</br>
![image](https://github.com/user-attachments/assets/6ffd845c-c7d8-41ed-b7da-f3e7b01f8f08)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Based on the image above, Taylor Swift has the highest number of tracks in the dataset with 34 songs. She is followed by The Weeknd with 22 tracks. Bad Bunny and SZA each have 19 tracks, and Harry Styles follows with 17 tracks.</br></br></br>


### Temporal Trends
#### * &nbsp;&nbsp;Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year. </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Before plotting, we first need to count the number of tracks released per year. Once we have this data, we should sort it in chronological order to make the plot easier to interpret. The code for this process is shown in the image below.</br>
![image](https://github.com/user-attachments/assets/10e70c74-5e97-4d56-93ac-febedbc92277)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After sorting, we can now plot it using a line plot shown in the image below.</br>
![image](https://github.com/user-attachments/assets/35c2882d-2f2f-4e5e-ab18-1c20257ffaa9)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The plot shows that from 1940 to the early 2000s, the number of tracks released per year remained low and stable. Starting in the 2000s, there was a steady increase, which became much more dramatic in the 2010s, peaking sharply around 2020. This trend suggests rapid growth in music production, likely driven by digital distribution and industry changes.</br></br>

#### * &nbsp;&nbsp;Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To do this we'll have to count the number of tracks released for each month, we can do this using the PANDAS code below.</br>
![image](https://github.com/user-attachments/assets/709cd297-acf0-4022-98dc-45813a481f04)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After counting the tracks per month, we can now plot it shown below.</br>
![image](https://github.com/user-attachments/assets/4a6d7263-87a0-4580-82a9-6c20dcabd37c)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Looking bar chart shows some clear trends in the number of tracks released each month. January and May have the highest number of releases, with each month featuring over 120 tracks. This suggests that these months are popular times for artists to release new music. On the other hand, August has the fewest releases, indicating a slower period for music releases. Overall, there seems to be a pattern where track releases are more frequent at the beginning and middle of the year, slow down during late summer, and then pick up again towards the end of the year.</br></br></br>


### Genre and Music Characteristics
#### * &nbsp;&nbsp;Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To analyze the relationship between streams and musical attributes like bpm, danceability, and energy, scatter plots are a useful tool. By plotting streams against each attribute, we can visually observe any patterns or trends. If a clear upward or downward trend appears, it suggests a correlation, indicating that changes in the attribute may influence streams. If the points are scattered randomly, it implies little or no relationship. This visual method is a straightforward way to see how musical features might impact streaming numbers. This can be shown on the image below.</br>
![image](https://github.com/user-attachments/assets/46c90fc9-383d-4f39-8968-1b9803178922)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We can see that in the first plot, there is no clear relationship between BPM and streams, as the data points are evenly spread across different BPM values, indicating that BPM alone may not strongly influence track popularity. The second plot, which examines danceability, suggests a subtle pattern where tracks with danceability percentages between 60% and 80% tend to receive more streams, hinting at a potential preference for moderately danceable music. Lastly, the energy plot shows that tracks with energy levels between 60% and 80% are slightly more likely to have higher stream counts. On conclusion, danceability and energy seem to have a modest impact on streams, while BPM does not appear to significantly affect a track's streaming performance.</br></br>


#### * &nbsp;&nbsp;Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Like the other correlation we first have to plot them. In this instance the best plot to use is the scatter plot since we are correlating data this can be done by doing the same thing done on the previous problem and is also shown on the image below.</br>
![image](https://github.com/user-attachments/assets/3b182da2-ed00-4fa9-86a8-33a86193e2ec)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Observing the plot between danceability and energy we can see that the plot shows a fairly scattered distribution but appears to have a slight upward trend. This might suggest a weak positive correlation, where tracks with higher danceability could be associated with higher energy.</br></br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Meanwhile, the plot between valence and acousticness shows that the plot reveals a more dispersed pattern, with many points clustered around low valence and low acousticness, but there is no clear, consistent trend. This may indicate a very weak or negligible correlation.</br></br></br>


### Platform Popularity
#### * &nbsp;&nbsp;How do the numbers of tracks in spotify_playlists, deezer_playlist, and apple_playlists compare? Which platform seems to favor the most popular tracks? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Before ploting we have to change the data type of the deezer playlist column into a numeric one since it is in object type shown on the image below.</br>
![image](https://github.com/user-attachments/assets/bdd8a39b-ca62-4926-9bfd-289181c613cb)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;But it looks like we have an error, which indicates that there are non-finite values in the column in_deezer_playlists. We can fix this by filling missing or undefined values with 0. After doing so we can now convert the data type into int as shown on the image below.</br>
![image](https://github.com/user-attachments/assets/ec39b249-a6b9-498e-9045-e723bc4410e3)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Now that we fixed the data type, We can use box plots to easily compare the number of tracks across Spotify, Deezer, and Apple playlists. The image below illustrates these comparisons, highlighting the differences in how each platform features tracks.</br>
![image](https://github.com/user-attachments/assets/2837d520-c019-4662-8394-23e28160dc6e)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Looking at the plots we can observe that spotify seems to favor the most popular tracks more prominently, as it allows for significantly larger playlists, giving more visibility to these tracks. Deezer and Apple, on the other hand, feature more moderate playlist sizes, with Apple having the most compact range. This suggests that Spotify's playlist strategy may aim to include a broader array of tracks, potentially benefiting more artists and tracks through extended exposure.</br></br></br>


### Advanced Analysis
#### * &nbsp;&nbsp;Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)? </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To answer the question similar to the previous ones we have to visualize it. We have to plot the key in relation to the streams, which helps identify if certain keys are associated with higher streams. We also have to plot the mode in correlation with the streams to see if one mode tends to have more streams on average. This can be seen on the images below.</br>
![image](https://github.com/user-attachments/assets/48973d19-7a87-4738-b10f-3f7372c84ca4)</br>
![image](https://github.com/user-attachments/assets/98143c5f-0345-4cf4-b513-2d3dd32fc506)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Observing the plots, we can see that while there are some variations in the potential for certain keys to produce more popular songs, the differences aren’t very dramatic. Both Major and Minor modes seem equally capable of generating hits, so the impact of key or mode on a song’s success may not be as strong as other factors, like genre or artist.</br></br>

#### * &nbsp;&nbsp;Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts. </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To answer the question we'll have to count the appearances of each artist across playlists or charts. Since there are three platfoms in the data set we'll have to count them per platform, we can do this using the codes below. </br>
![image](https://github.com/user-attachments/assets/1146f8ab-b731-4943-ab3e-8e5a4d4fa4f5)</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After counting how frequent the artists appear in each playlist platforms, we can use a bar plot to be able to analyze it easier. This can be shown on the images below.</br>
![image](https://github.com/user-attachments/assets/0ba3aee2-bb69-4e0b-af20-80881470ea7a)</br>
![image](https://github.com/user-attachments/assets/7eacdf87-be54-4112-99ae-17e347b3b404)</br>
![image](https://github.com/user-attachments/assets/df947bb4-c5af-456a-82c6-0d699aeac8e0)</br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We can see that there is a noticeable consistency in certain artists appearing across different platforms' charts, with Taylor Swift, Harry Styles, The Weeknd, and Ed Sheeran being among the most recurrent. This reflects their wide appeal and genre-spanning hits. Pop, pop-rock, hip-hop, and alternative/indie are the most frequently represented genres, showing their universal reach and broad listener base.
