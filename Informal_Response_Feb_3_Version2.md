## Question 1
##### In Laurence Maroney’s video, What is ML, he compares traditional programming with machine learning and argues that the main difference between the two is a reorientation of the rules, data and answers. According to Maroney, what is the difference between traditional programming and machine learning?
My Response: 
When it comes to traditional programming, the rules and data are the input or the materials that leads to the traditional programming. As an output, we get the answer. On the other hand, the answers and the data that are processed with labeling are the input, followed by the training of neural network/neurons. Finally, we will get the rules as the output. 

## Question 2 
##### With the first basic script that Maroney used to predict a value output from the model he estimated (he initially started with 10 that predicted ~31. Modify the predict function to produce the output for the value 7. Do this twice and provide both answers. Are they the same? Are they different? Why is this so?
My Response: 
Trial 1 - - 22.0017. Trial 2 - 21.999985. They are different because we only have six data points for training. The neural network deal with probabilities. Hence, with the limited data points, the results varies based on the different pattern that occur in each training model. 

## Question 3
##### Using the script you produced to predict housing price, take the provided six houses from Mathews, Virginia and train a neural net model that estimates the relationship between them. Based on this model, which of the six homes present a good deal? Which one is the worst deal? Justify your answer.
Original Response:
I used house price and the number of bedrooms as the parameters for the two arrays. Disregarding the location of the house, the size of the house, and the number of bathrooms, I think the best deal for people who has a strict budget is definitely the house on Holly Point Rd, with the price of $97,000 and three bedrooms. It provides three bedroom, which is about the average number of the bedrooms considering the six houses. Though the single bathroom is going to be a major concern, the price outweighs all the other houses. Without the budget restriction, I would say the house on **4403 New Point Comfort Hwy**, with the price of $229,000 and three bedrooms, is the **best deal** out of the six houses. With the trained model, I predicted the model with 3 bedrooms, it gave back the result of 1.63. It is obviously the less costly option out of the five houses (excluding the $97,000 house). I would argue the location and an addition bathroom increases the value of the house as well. The **worst deal** would go to the house on **Fitchetts Wharf Rd**, with the price of $250,000 and two bedrooms. With the trained model, I predicted the model with 2 bedrooms, it gave back a result of 1.7, which I assume is suggesting the more reasonable price, considering the 2 bedrooms.   

**New Response**:
To determine whether it is a good deal, we have put three factors into considerations. They are the number of bedrooms, the land mass in square feet, and the number of bathrooms. They are organized into three arrays of datapoints. To start off, I looked at the most expensive house, which is labeled as church. After inserting all the data point related to the "church" house, the prediction result was approximately 3.72 (compared to 3.99), which tells us the more reasonable price for the house. Compared it to the proposed price, it is **not a good deal**. The second house I looked at was hudgins. The prediction result was 1.59 (compared to 0.97), which is a **good deal** compared to the proposed price. The third hosue was mathews. The prediciton result was 3.06 (compared to 3.475), it is **not a good deal**. The fourth house was mobjack. The prediction result was 3.22 (compared to 2.89). It is a **good deal**. The fifth house was moon. The prediction result was 1.59 (compared to 2.5). It is **the worst deal** out of all the six houses. Last but not least, the sixth house was newptcomfort. The prediction result was 2.83 (compared to 2.29), which is a **good deal**.  

#### Code Example for the worst deal - moon
model = tf.keras.Sequential([keras.layers.Dense(units=1,input_shape=[3])])
model.compile(optimizer='sgd',loss='mean_squared_error')
x1 = np.array([4.0,3.0,4.0,5.0,2.0,3.0],dtype=float) #Number of Bedroom
x2 = np.array([3.524, 2.840, 3.680, 3.051, 1.479, 1.238], dtype =float) # Square Feet
x3 = np.array([2.0,2.0,3.0,2.0,1.0,1.0], dtype=float) # Number of bathrooms

xs = np.stack([x1,x2,x3], axis=1)
ys = np.array([2.89,2.29, 3.99, 3.475,2.5,0.97],dtype=float) #House Price in Hundred Thousands

model.fit(xs,ys,epochs=1000)

a = np.array([2.0],dtype=float)
b = np.array([1.479],dtype=float)
c = np.array([1.0],dtype=float)
d = np.stack([a,b,c], axis=1)
model.predict([d])

