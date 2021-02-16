## Mini Project 1 - Social Distance Detector  (Feb.14)

### - Was your social distance detector effective at detecting potential violations? 
It is effective at detecting small group of people and calculating the distance between people. When it comes to a herd of people standing next to each other, it could have been better if we changed the code slightly by reducing the range of the square detector. Hence, we can identify each individual within a large group of people. 

### - Are you able to describe how the distance detector is applying its calculations of either being safe or noting a violation?
For each individual, the social distance detector creates a rectangular frame around a person. If the border color of the rectangluar frame is green, the person is following the social distance protocol; if the border color of the rectangular frame is red, indicating the person is violating the social distancing protocol based off the detector model. Regarding the output of the video, a group of people can be misrepresented as a greater size of rectangular frame.

### - Do you think this approach would be effective for estimating new infections in real time? How would you implement such an approach in response to the COVID-19 pandemic we are currently experiencing?
I don't think this detector model would be that effective. With the current efficiency of the algorithm, it will require a massive amount of time to run the prediction. The time might be reduced if I have access to computers with better hardware. In general, I think this is a good method to help evaluate the risk level in different regions, especially the ones with higher population density. 

### - What limitations or improvements might you include in order to improve your proposed design?
I think some improvements include the facilitation of detection from different angles. Like we mentioned during class, we can test it via bird view. Moreover, I think the design can be even more powerful when we can identify people of different age groups, based on variables such as height, hair color, and the speed they are walking...etc. Perhaps we can also add in another color code for objects/vehicles.  

### - [Input Video](https://youtu.be/bBj7QqmFNPw) (First 30 seconds of the video)
### - [Output Video Link](https://youtu.be/8-QGmq2gROc) (Total Time Taken: 16 mins)
