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

![screenshot from 2018-05-30 00-09-31](https://user-images.githubusercontent.com/35591154/40668137-b48687d8-639e-11e8-9ccc-3ff28a442ad7.png)

----
## Visualize Data

class number & each percentage about the total

![screenshot from 2018-05-30 00-11-45](https://user-images.githubusercontent.com/35591154/40668268-01749094-639f-11e8-911b-c9451560889b.png)

Below the picture are the number of each class number and the total number of images for each class in the test set.

----
## Preprocess Data

convert RGB images to GRAY images

There are very dark images. 

Class 19

![screenshot from 2018-05-30 00-30-33](https://user-images.githubusercontent.com/35591154/40669359-ba7e418c-63a1-11e8-817e-7212549bf1ff.png)

Class 20

![screenshot from 2018-05-30 00-29-10](https://user-images.githubusercontent.com/35591154/40669358-b9a87264-63a1-11e8-9ce1-25e4599647c7.png)

If I use these images as input for learning, the accuracy of CNN model will decrease. So I try to convert these images to gray color.

Class 19

![screenshot from 2018-05-30 00-30-45](https://user-images.githubusercontent.com/35591154/40669572-338ef544-63a2-11e8-8a7b-012af35c4ef9.png)

Class 20

![screenshot from 2018-05-30 00-29-19](https://user-images.githubusercontent.com/35591154/40669580-355b0f66-63a2-11e8-9541-99c8ce5367cd.png)

The outline of the traffic sign is much detectable than that of the RGB color. Thus, the entire data is converted to gray color.

----
## Normalization the data

Normalize all data. Divide each data by size, subtract the mean, and divide by the standard deviation.

## Shuffle the training data

The model should not be affected by the order of the data to be learned. Therefore, the data to be learned must be randomly mixed.

## Model Architecture


