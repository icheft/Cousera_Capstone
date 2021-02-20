<h1 align='center'>
<br>
<img src="assets/IBM-Logo.png" alt="IBM Course" width="200">
<br>
 Applied Data Science Capstone
</h1>
<p align="center">
  <a href="#updates">Updates</a> • 
  <a href="#course-syllabus">Course Syllabus</a> • 
  <a href="#the-battle-of-neighborhoods">The Battle of Neighborhoods</a>
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

## The Battle of Neighborhoods

### Identity the Problem
**1. The description of the problem and the discussion of the background.**

Taiwan is known for its outstanding performance throughout this pandemic, and students from all over the world urge to know more about the unique island. Taiwan strictly performs its regulation and carries out a 14-day quarantine for people who are allowed to enter the island, including Taiwanese citizens. 

Besides the restrictions, Taiwan is also known for its high population density (ranked 17th worldwide in 2019 according to [statista](https://www.statista.com/statistics/264683/top-fifty-countries-with-the-highest-population-density/)), beautiful mountains, and convenience. 

As a student currently studying in Taiwan, providing an insightful analysis to the local universities in terms of convenience would be interesting for future students when it comes to choosing which university to go to. Moreover, as a gym-goer and a sports fanatic, picking an university surrounded by sports facilities is always considerable. 

The project is then aiming (1) to examine the neighborhood of each university in Taiwan, exploring how it is like to live on campus, and (2) to inspect the potential location to run a gym business for huge fitness clubs like Fitness Factory and World Gym. 


**2. The description of the data and hot it will be used to solve the problem.**

+ The data of listed universities is from the Ministry of Education, which can be found [here](https://ulist.moe.gov.tw/Download/FileDownload). The list contains attribute include:
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

Since longitude and latitude for each school is not listed, [HERE](https://developer.here.com) API is used to fetch the data needed to be further processed using Foursquare.

+ The geojson data for Taiwan is provided by [g0v](https://github.com/g0v/twgeojson). Since the data hasn't been updated for nearly 6 years, some content from the dataset needs to be corrected.
  + I'm fetching [this](https://raw.githubusercontent.com/g0v/twgeojson/master/json/twCounty2010.geo.json) geojson data. As an example of the correction, 桃園縣 (Taoyuan County) needs to be corrected to 桃園市 (Taoyuan City).