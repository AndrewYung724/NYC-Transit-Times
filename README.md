# NYC-Transit-Times
We attempt to solve this problem in New York City, which is unsurprisingly one of the most difficult places in the world to predict ETA because of the dense population and large variation in traffic and other factors out of our control. Aside from the pick-up and drop-off locations, we also consider the day of the week and time of day when calculating the shortest ETA since these tend to be the most important factors. Ideally, we would be able to incorporate factors that other mapping services use such as speed limits, the density of traffic lights, shortest-distance routes, traffic patterns, weather, and much more, but this became infeasible for us due to the extremely high amount of complexity involved.

We chose to utilize data from past recorded trips, specifically from the NYC Taxi and Limousine Commission throughout the entirety of 2016 with almost 1.5 million data points. The variables recorded include date and time that taxi meters were engaged and disengaged for a trip, the number of passengers, latitude/longitude coordinates of the pick-up and drop-off locations, and the total trip duration (which the data set had already calculated for us).

We applied different regression analysis techniques to come up with a final model that would predict the ETA of a trip by car. Although the model would not be perfect, it would be able to inherit the effects and frequency of these uncontrollable factors since the model uses real-life data. In this report, we discuss our mathematical model for performing the regression, along with an alternative model that ultimately did not suit the problem as well. We then show how we pre-processed the data and performed the regression using different subsets of the data for more insight into how the ETA could vary based on the variables recorded in the data. 

Model 1: 
We are using the one norm because traffic congestion is primarily based off of distance and additional time from traffic. If we choose to have distance as our primary prediction method and we know Distance=Speed*Time then we can use the one norm with a multiplied to distance plus another for every specific time interval to account for traffic.

![image](https://user-images.githubusercontent.com/38053500/153941921-05c0a213-4763-41f5-9ab6-3931ba35ff38.png)


Model 2:  
We also have the least squares as an option for our model because it is a well-known model that is commonly used. However, with the given data set outliers did have a negative effect on our regression.

![image](https://user-images.githubusercontent.com/38053500/153941952-766e553c-a699-4ee1-8caa-40370df6a4fe.png)



When analyzing the data and looking for patterns our model could work off of we found the following trends with traffic.
![image](https://user-images.githubusercontent.com/38053500/153941757-170d104e-7589-4820-9a7c-a9851d7852ec.png)

As a result of our linear regression across the various features noted in table 1.
![image](https://user-images.githubusercontent.com/38053500/153942163-9bd1a40d-4b14-4d44-9a3c-b709b9581129.png)

We achieved the following training and test errors across several feature sets.
![image](https://user-images.githubusercontent.com/38053500/153942106-51b174b4-3d8f-469c-b4cf-d142ab727a9d.png)
