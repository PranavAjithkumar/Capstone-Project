# Capstone-Project

1) Introduction/Business Problem

The business problem will be to use the Foursquare API data to find which areas are populated the most and form predictions on upcoming areas. For example, if a certain area gets a lot of housing developments, therefore nearby areas should be able to use that attention to build up their market. The foursquare api will be used to find which areas are most populated in toronta and from there figure out where to form the next business. This data would be useful to the client, as it would tell them which areas are beneficial for business. They could put ads around the area or if they are looking to relocate or start their business, it would allow them to judge the area accordingingly 

2) Downloading and Prepping Data

https://open.toronto.ca/dataset/neighbourhoods/
This link will be used to find neighborhood to find most populated areas. By using this data , a predicitive model may be able to be formed to find the areas where population is high, hence businesses could prosper. This data will show the correlation between prospering areas and neighborhoods and can be used to help clients find where the best business can be found.

3) Methodology

Firstly, we need to get the list of neighbourhoods in the city of Toronto, Canada using this link: https://open.toronto.ca/dataset/neighbourhoods/. I imported this data as a csv file and cleansed the data. The prepped data will show the area/city name, lattitude and longitude. We built the geographical coordinates in order to work with the Foursquare API. From there the geocoder package was utilized to get the map of Toronto and superimposed these neighborhoods onto the map using folium. We used the Foursquare API to get 139 venues within 2000 meter radius. This was done by following the instruction in week 4 to set up a developer account in Foursquare. The API call included extra parameter called categoryId and used category value of '4e67e38e036454776db1fb3a' to get the residential categories, along with lattitude and longitude of each neighborhood. We limited ourself up to 50 calls. The API returned a JSON dataset with venue name, venue category, venue latitude and longitude. This is appeneded to our dataframe. We extracted all unique categories in this city name and then decided to use housing development category. We analyzed each
city name by grouping the rows by city name and taking the mean of the frequency of
occurrence of each venue category. From there, the data was clustered for using the housing development. Finally, clustering on the data was performed using k-means clustering. It used k numbers of centroids and had 3 clusters. This result will show us how many housing developments there were per cluster. 

4) Results

There are 110 with Cluster Labels=0.
There are 6 with Cluster Labels=1.
There are 12 with Cluster Labels=2.


5) Discussions

In the Discussion, we will discuss our results. Based of the clusters, you can see cluster label 0 has 110 housing developments. From that we can concur, that most the population lives in this cluster neighborhood. line 44 gives specific citynames. 

6) Conclusion

Based on population, it would be best to start a new business where there is a highly dense neighborhoods of clusters. This can be found in label 0. 


 
