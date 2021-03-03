# Informal Response 4 - Matrix Convolutions & Mean Squared Error - Feb.26.2021

## Convolutions
### My First 3x3 matrix 

```
[[1,0,0],
 [0,0,0],
 [0,0,1]]
```

### My Second 3x3 matrix 
```
[[0,0,0],
 [0,1,0],
 [0,1,1]]
```

### My 9x9 Matrix
```
[[0,0,0,0,1,-1,1,-1,1],
 [-1,-1,0,2,1,0,-1,0,-1],
 [1,-1,0,0,2,-2,0,-1,0],
 [-1,0,-1,0,-1,1,0,0,-1],
 [0,0,0,0,-2,0,-1,1,1],
 [1,-1,0,-1,1,1,-1,0,-1],
 [0,1,-1,1,-2,0,-1,-1,-1],
 [-1,1,1,-2,1,0,-1,0,-1],
 [0,1,-1,-1,2,1,0,0,1]]
```

### First Matrix convolution Result
```
[[ 0, 0, 2,-2, 1,-2, 1],
 [-2, 1,-1, 3, 1, 0,-2],
 [ 1,-1,-2, 0, 1,-1, 1],
 [-1,-1, 0, 1,-2, 1,-1],
 [-1, 1,-2, 0,-3,-2,-1],
 [ 2,-3, 1,-1, 0, 1,-2],
 [-1, 0, 1, 2,-2, 0, 0]]
```
### Second Matrix convolution Result 
```
[[ 0, 0, 4, 1,-2,-2,-1],
 [-2,-1,-1, 2,-1, 0,-2],
 [ 0,-1,-2,-3, 0, 0, 2],
 [-1,-1, 0, 0, 0,-2, 0],
 [-1, 0,-2,-1, 0,-3,-2],
 [ 3,-2, 0,-1,-1,-2,-2],
 [-1,-1,-1, 4, 1,-1, 1]]
```

### What is the purpose of using a 3x3 filter to convolve across a 2D image matrix?
This is a common image processing technique. With the 3x3 filter, it is often used to detect the edges of the image and sharpening the features of the image. With my given matrix, the first 3x3 matrix should be more effective in edge detection since it is looking for the pixels locating at the opposite corners. 

### Why would we include more than one filter? How many filters did you assign as part of your architecture when training a model to learn images of numbers from the mnist dataset?
We want to include more than one filter for the convolutional network so we can train a better model. Since each filter can learn one pattern, the model will be more confident in identifying the characteristics of the object or person by applying multiple filters. From a time efficiency standpoint, we include more than one filter at the same time to save the computational time.

## Mean Squared Errors
### The 10 biggest over-predictions
MSE = 338679.65946653986
### The 10 biggest under-predictions 
MSE = 4630377.550264684
### The 10 most accurate results (use absolute value)
MSE = 48.94480008462041

### Which feature appears to be the most significant predictor in the above cases?
Taking at a look at the over-predictions, I realize how the mean of the bedrooms and bathrooms are consistent, but the square footage has a wide range. Hence, this feature appears to be the most significant predictor, based on the over-predictions observations. On the other hand, I think it is ambiguous for under-predictions model. The three predictors seem to be consistent. I would assume that the location is the more significant predictor. Hence, I could validate that if I take a look at zipcode. 
