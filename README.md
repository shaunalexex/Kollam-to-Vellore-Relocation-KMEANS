# Kollam to Vellore Relocation using K-Means Clustering

## TABLE OF CONTENTS

* INTRODUCTION/BUSINESS PROBLEM
* DATA DESCRIPTION
* METHODOLOGY
* ANALYSIS
* RESULTS AND DISCUSSION
* CONCLUSION

## INTRODUCTION / BUSINESS PROBLEM

This project is based on a problem that my friend faced in college. I currently study at Vellore Institute of Technology, Vellore as a 4th year Engineering student. My friend and I both moved from Kerala, India to Tamil Nadu, India for our higher studies. While moving to a new location it can be really tough to find out the right location on the basis of accessibility, distance, services etc. With this project I am looking to help my friend who is based in Kollam, Kerala to find the right location to shift to in Vellore, Tamil Nadu. 
The reason I consider this to be a tough problem is because Vellore is quite underdeveloped and it can be hard to find a place to live, while Kollam is quite developed with lots of different venues and locations of different types. So for someone who is moving from an area like Kollam to VIT Vellore, this project will try to find similar locations in Vellore to locations in Kollam using clustering. Here the k means clustering algorithm is used to achieve the task. Folium library can be used to visualize the clusters in both cities
The major Target Audience for this project will be those looking to relocate from one city to another. In this project we are exploring the possibility of moving from Kollam to Vellore but this idea can be utilized in other similar cases as well.

## DATA DESCRIPTION

For this project I will first leverage data from the web to find out the neighbourhoods in Kollam and Vellore using BeautifulSoup for web scraping.
	
  1. https://en.wikipedia.org/wiki/List_of_areas_of_Vellore
  2. https://en.wikipedia.org/wiki/List_of_neighbourhoods_of_Kollam
  
  I also used the FourSquare API to obtain all the venues within 2000 metres of the location. Using this venue data we will be able to find locations in vellore with a similar profile. In this case I will not be filtering down the venues based on the number of venues returned since it is important that people looking for places with high accessibility and low accessibility both find their area of interest. Thefollowing data are obtained from the Foursquare API:
  1. Venue
  2. Venue Latitude
  3. Venue Longitude
  4. Venue Category Data

Initially we obtained a total of 81 different categories but there were a lot of categories that were similar and could be combined like Fast Food Restaurant and Fried Chicken Restaurant. This took some hands on work but I reduced the categories down to 70 by combining those that were really similar.

## METHODOLOGY

After obtaining the list of neighbourhoods from the links and obtaining the venues near the neighbourhoods using the FourSquare API. After this I one hot encoded the data. Then used Kmeans algorirthm to cluster the data with number of clusters set to 5. 
The clusters obtained can be analyzed to find which locations are similar between Kollam and Vellore.
After obtaining the results we can sort the them based on the distance to VIT university and select the best options.

## ANALYSIS
***Neighbourhoods in Kollam***
![kollam_neighbourhoods](https://octodex.github.com/images/yaktocat.png)
***Clusters in Kollam***
![kollam_clusters](https://octodex.github.com/images/yaktocat.png)
***Neighbourhoods in Vellore***
![vellore_neighbourhoods](https://octodex.github.com/images/yaktocat.png)
***Clusters in Vellore***
![vellore_clusters](https://octodex.github.com/images/yaktocat.png)

## RESULTS

***Neighbourhoods in Vellore similar to Kilikollur, Kollam***
![kilikollur](https://octodex.github.com/images/yaktocat.png)

***Neighbourhood sorted by distance to VIT***
![result](https://octodex.github.com/images/yaktocat.png)

## CONCLUSION

***In this project I have successfully found relocation options for my friend who is considering moving from Kollam to Vellore and filtered the options with respect to closeness to his University***
