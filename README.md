# surfs_up

# Surf's Up with Advanced Data Storage and Retrival

## Overview of Project

### Purpose

The purpose of this project is to help analyse how a surf and ice cream shop would do in Oahu, Hawaii. Using tools like SQLite and SQLAlchemy we can quickly manage large amounts of data with out the need and hassle of setting up a database server and making a database for our information. SQLAlchemy lets you query a local database with python  using simple commands that preform the same tasks as writing SQL query code. In this project we will use these tools to get data from an SQLite file that has 6 years worth of data of temperature and precipitation. We are asked to use query commands to collect data for June and December and run a statistical analysis on it.

## Results

To find the results of this we needed to use SQLAlchemy to query our SQLite database. I used the following code to get the information that was required for the data that I needed.

![image](https://user-images.githubusercontent.com/92827264/152701964-477b9b98-ef52-4c65-9871-98a11967fdef.png)

I put this data into a dataframe and used the describe function on it to obtain the following result.

![image](https://user-images.githubusercontent.com/92827264/152702003-a7b85dca-923e-436e-aa33-3b91f55cb148.png)

I used the same query but changed the date to look for '%-12-%' to gather all the data for the month of December. I also put this data into a dataframe and used the describe function on it to obtain this result.

![image](https://user-images.githubusercontent.com/92827264/152702081-826eb0a5-a717-4f14-ad60-cb96bb65831a.png)

When looking at the statistics for both months. You can see some key differences

- Min temperature is lower in December by 8 degrees.

![image](https://user-images.githubusercontent.com/92827264/152703932-a2bb7346-da24-4631-a62a-8195d3d58435.png)
![image](https://user-images.githubusercontent.com/92827264/152703935-81ba16f0-f2a0-4a85-9973-8c5dcd63026d.png)


- The standard deviation is higher by half a degree. That means the temperature swings will be a little bigger through the month.

![image](https://user-images.githubusercontent.com/92827264/152703947-4bfd64aa-a397-4940-854f-141630338d42.png)
![image](https://user-images.githubusercontent.com/92827264/152703952-cb2b7350-9abf-4750-8e8a-86a3934e2450.png)


- The all other temperature ranges are 4 degree difference or less. So the average difference in temperature change between the months is 4 degrees.

![image](https://user-images.githubusercontent.com/92827264/152703965-9d2ef11b-7509-4ece-b34e-333fdab25b39.png)
![image](https://user-images.githubusercontent.com/92827264/152703975-6a54e9e0-0c5e-45f4-992c-71ce2986b30d.png)


## Summary

To summarize the findings, there is are a few key differences between the two months. The biggest difference is the how cold it gets in December. There is a 8 degree difference in the minimum temperature with the low being 56 degrees. That is a pretty low temperature and would likily not be selling that many ice cream shakes when the temperature is getting that low. There is about a half degree higher standard deviation in the temperature which means that the temperature swings are higher. There is not much of a difference in the max temperature between the months so it still gets just as hot as in June.

Another query that can be run for more data would be to add the precipitation data for the months. The surf/ice cream shop will have less activity on rainy days. The query I would run is "session.query(Measurement.date, Measurement.tobs, Measurement.prcp).filter(Measurement.date.like('%-12-%')).all()". If this is done for both months it will give more information on how rain will affect the surf shop in both June and December.
