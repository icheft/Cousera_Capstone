<h1 align='center'>
<br>
<img src="assets/IBM-Logo.png" alt="IBM Course" width="200">
<br>
 Applied Data Science Capstone
</h1>
<p align="center">
  <a href="#updates">Updates</a> • 
  <a href="#course-syllabus">Course Syllabus</a> • 
  <a href="#the-battle-of-neighborhoods">The Battle of Neighborhoods</a> • 
  <a href="#references">References</a>
</p>

## Updates

## Course Syllabus
### Week 1 - Introduction to Capstone Project

+ Introduction to Capstone Project
+ Location Data Providers
+ Signing-up for a Watson Studio Account
+ Peer-review Assignment: Capstone Project Notebook
### Week 2 - Foursquare API

+ Introduction to Foursquare
+ Getting Foursquare API Credentials
+ Using Foursquare API
+ Lab: Foursquare API
+ Quiz: Foursquare API


### Week 3 - Neighborhood Segmentation and Clustering

+ Clustering
+ Lab: Clustering
+ Lab: Segmenting and Clustering Neighborhoods in New York City
+ Peer-review Assignment: Segmenting and Clustering Neighborhoods in Toronto
### Week 4 & 5- Capstone Project

<h1 align='center'>
<br>
    <img src="./assets/ibm_x_taiwan.png" alt="IBM Course" width="400">
<br>
    Applied Data Science Capstone
</h1>


<h2 align='center'>
The Battle of Neighborhoods - A Look Around Universities in Taiwan
</h2>

<h5 align='center'>
    Brian L. Chen, Feb., 2021
</h5>


### 1. Introduction

#### 1.1 Background
Taiwan is known for its outstanding performance throughout this pandemic, and students from all over the world urge to know more about the unique island. Taiwan strictly performs its regulation and carries out a 14-day quarantine for people who are allowed to enter the island, including Taiwanese citizens. 

Besides the restrictions, Taiwan is also known for its high population density (ranked 17th worldwide in 2019 according to [statista](https://www.statista.com/statistics/264683/top-fifty-countries-with-the-highest-population-density/)), beautiful mountains, and convenience. 

As a student currently studying in Taiwan, providing an insightful analysis to the local universities in terms of convenience would be interesting for future students when it comes to choosing which university to go to. Though it may be somewhat absurd only choosing universities based on their convenience, it is still something worth noticing, especially for those who haven't actually been to a specific university before. 

Moreover, as a gym-goer and a sports fanatic, picking an university surrounded by sports facilities is always considerable. 

#### 1.2 Interest 

The project is then aiming (1) **to examine the neighborhood of each university in Taiwan, exploring how it is like to live around its neighborhood**, and (2) **to inspect the sports facilities around each university in Taiwan**. 

The aim is to help future students choose their universities in terms on what their neighborhoods have to offer and what they would like to experience. The second part of this project could also help students playing sports gain a better perspective on which school to go to based on their preferences. 


<div class='alert alert-block alert-warning' style='margin-top: 20px'>
🗒️ Notice<br>
I am not here to get involved in any political issues. Taiwan is a beautiful place with beautiful people, and the project aims to provide insights regarding the universities on the island. Please do not add extra political perspective towards this project.
</div>

![](https://dynaimage.cdn.cnn.com/cnn/q_auto,w_900,c_fill,g_auto,h_506,ar_16:9/http%3A%2F%2Fcdn.cnn.com%2Fcnnnext%2Fdam%2Fassets%2F180719131350-beautiful-taiwan-popumon-alishan.jpg)

### 2. Data Acquisition and Cleaning

#### 2.1 Data Sources
##### 2.1.1 List of Accredited Taiwan Universities
The data of listed universities is from the Ministry of Education, which can be found [here](https://ulist.moe.gov.tw/Download/FileDownload). The data contains the following information:

+ School ID
+ Private/Public Status
+ System/Institution
+ University Name (in Chinese)
+ University Name (in English)
+ Principal of the university
+ County
+ School District
+ Postal Code
+ School Address (in Chinese)
+ Tel
+ School Website

Since longitude and latitude for each school is not listed, **[HERE API](https://developer.here.com)** is used to fetch the data needed to be further processed using Foursquare. The final outcome is *stored locally* so that the API calls will not be provoked everytime when I restart the kernal.

The final attributes include:

+ Serial Number 
+ ID
+ Public/Private
+ System
+ Name
+ Eng. Name
+ Postal Code
+ Latitude
+ Longitude
+ Address
+ City
+ County
+ Neighborhood
+ County (zh)

##### 2.1.2 Geojson Data of Taiwan
The **geojson data** of Taiwan is obtained to plot the choropleth map. The data helps define the boundaries for each county in Taiwan. It is provided by **[g0v](https://github.com/g0v/twgeojson)**. Since the data hasn't been updated for nearly 6 years, some content from the dataset needs to be corrected.

I'm fetching [this](https://raw.githubusercontent.com/g0v/twgeojson/master/json/twCounty2010.geo.json) particular geojson data. As an example of the correction, 桃園縣 (Taoyuan County) needs to be corrected to 桃園市 (Taoyuan City). 
  
##### 2.1.3 Information of Venues Around Universities
[Foursquare API](https://developer.foursquare.com) is used to obtain the final list of venues to be further examined. Also note that Foursquare API uses special "category id" for each category. Since I am collecting a series of fitness/gym sites, scraping (instead of connecting through [its API](https://developer.foursquare.com/docs/api-reference/venues/categories/) the [venue category page](https://developer.foursquare.com/docs/build-with-foursquare/categories/) works better for me. I am collecting data with the following information:

+ University (zh)
+ University (eng)
+ University Latitude
+ University Longitude
+ Venue
+ Venue Latitude
+ Venue Longitude
+ Venue Category

##### 2.1.4 Results
Last but not least, there would be a total of **five** datasets to make analysis from: 

1. Venues within 1,500m for each university on the list - to examine the convenience of each university
2. Sports venues within 1,000m and 2,000m
3. Gym venues only within 1,0000m and 2,000m
### 3. Methodology

Please see the ipython notebook or the full report for more details. 

section which represents the main component of the report where you discuss and describe any 

exploratory data analysis that you did, any inferential statistical testing that you performed, if any, and what machine learnings were used and why.

Exploratory Data Analysis



Machine Learning

## References
+ <https://towardsdatascience.com/the-easiest-way-to-interpret-clustering-result-8137e488a127>
+ <https://www.datanovia.com/en/lessons/determining-the-optimal-number-of-clusters-3-must-know-methods/>
+ <https://github.com/g0v/twgeojson>