# Udacity SDCND Project_3
# Traffic Sign Classifier

----

## Load The Data
Download [dataset](https://d17h27t6h515a5.cloudfront.net/topher/2017/February/5898cd6f_traffic-signs-data/traffic-signs-data.zip)

This file contains separate data for test, validation, and trianing.

Import the pickle library to read the file and store the data in the variable.

----
## Dataset Summary
The picture in the input file has RGB color and is 32 * 32 pixels in width and height. 

![screenshot from 2018-05-29 23-14-18](https://user-images.githubusercontent.com/35591154/40667895-2e94817a-639e-11e8-8c88-9326f1a19d5d.png)

The class id of the German signs and corresponding meanings.

![screenshot from 2018-05-30 10-36-56](https://user-images.githubusercontent.com/35591154/40694189-5cca8c62-63f6-11e8-9b77-acec8907705a.png)

----
## Visualize Data

class number & each percentage about the total

![screenshot from 2018-05-30 00-11-45](https://user-images.githubusercontent.com/35591154/40668268-01749094-639f-11e8-911b-c9451560889b.png)

Below the picture are the number of each class number and the total number of images for each class in the test set.

----
## Preprocess Data

convert RGB images to GRAY images

As you can see when visualizing your data ,there are very dark images. 

Class 19

![screenshot from 2018-05-30 00-30-33](https://user-images.githubusercontent.com/35591154/40669359-ba7e418c-63a1-11e8-817e-7212549bf1ff.png)

Class 20

![screenshot from 2018-05-30 00-29-10](https://user-images.githubusercontent.com/35591154/40669358-b9a87264-63a1-11e8-9ce1-25e4599647c7.png)

If I use these images as input for learning, the accuracy of CNN model will decrease. So I try to convert these images to gray color.

Class 19

![screenshot from 2018-05-30 00-30-45](https://user-images.githubusercontent.com/35591154/40669572-338ef544-63a2-11e8-8a7b-012af35c4ef9.png)

Class 20

![screenshot from 2018-05-30 00-29-19](https://user-images.githubusercontent.com/35591154/40669580-355b0f66-63a2-11e8-9541-99c8ce5367cd.png)

The outline of the traffic sign is much detectable than that of the RGB color. Thus, This kind of image is better to convert colors. If so, look for images that are somewhat distinguished by RGB colors.


![screenshot from 2018-05-30 11-10-26](https://user-images.githubusercontent.com/35591154/40695283-8ddad654-63fb-11e8-9c6a-b034a628e0cd.png)
![screenshot from 2018-05-30 11-10-36](https://user-images.githubusercontent.com/35591154/40695285-8f3d4eaa-63fb-11e8-988f-fa19eaedc743.png)


![screenshot from 2018-05-30 11-18-18](https://user-images.githubusercontent.com/35591154/40695416-23868b80-63fc-11e8-94ea-6b0e9bcc55ad.png)
![screenshot from 2018-05-30 11-18-27](https://user-images.githubusercontent.com/35591154/40695418-24cd8516-63fc-11e8-8289-63778e624b18.png)

This conversion also makes images that are somewhat distinguishable in RGB more vivid. So Applying this process to the whole data will improve learning accuracy.

----
## Normalization the data

Normalize all data. Divide each data by size, subtract the mean, and divide by the standard deviation.

## Shuffle the training data

The model should not be affected by the order of the data to be learned. Therefore, the data to be learned must be randomly mixed.

## Model Architecture

Original structure is like this.

![screenshot from 2018-05-29 22-40-26](https://user-images.githubusercontent.com/35591154/40694719-c6d09bae-63f8-11e8-8009-a2f4e24edcb0.png)

I changed the depth of the layer more deeply and applied a dropout with a 75% probability to prevent overfitting.
I had used average pooling instead of max pooling in the pooling process,but the result of the max pooling was better. So I use max pooling. 

## Optimaze loss function of difference between logits(pridected classes) and actural classes(labels in input data)

Test data is as large as 35,000 data. Therefore, it is more efficient to optimize, or minimize , the loss by applying the gradient descent to randomly extracted data from the whole rather than to the whole data.
Thus, I use a stochastic gradient descent algorithm **AdamOptimizer** instead of using the basic gradient descent algorithm.

## Model evaluation

To evaluate the outcome of learning, compare the predicted and actual values. And see how well the predictions are in graph.

## Train the model and than validate&test it

It repeats learning as much as epoch. Then calculate the accuracy of the training & validation & test.
Then save the learned model to a file. This ensures that I will not have to re-learn the model unnecessarily when testing for new images later. 

The results are as follows. The target of the validation accuracy is more than 93%, about 95%. The test accuracy is about 93.5%.

![screenshot from 2018-05-30 11-57-05](https://user-images.githubusercontent.com/35591154/40696626-8be00904-6401-11e8-8ebc-756050b4ee36.png)

![screenshot from 2018-05-29 23-34-37](https://user-images.githubusercontent.com/35591154/40696630-8e7d80b0-6401-11e8-91a0-367f88200ce6.png)

