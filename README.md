# Udacity SDCND Project_3
# Traffic_Sign_Classifier
#### In this project, I use a LeNet-5 convolutional neural networks to implement a classifier to distinguish German traffic sign. LeNet-5 is the most basic structure of the CNN. 

![screenshot from 2018-05-29 22-40-26](https://user-images.githubusercontent.com/35591154/40664108-2610fce4-6395-11e8-9da5-16ff82f9abf5.png)

#### After the conv layer and the pooling layer are repeated twice, fully connected connection layer is used three times.
----

## Process
- ### Load The Data

In the given file, load the data in the following format

Number of training examples = 34799

Number of validation example  4410

Number of testing examples = 12630

Image data shape = (32, 32, 3)

Number of classes = 43




- ### Dataset Summary & Exploratory Visualization

visualize an image about each label and represent the ratio of the element number of the each class to total.

- ### Preprocess Data

Convert the image to gray color and normalize it for better learning.

- ### Design LeNet-5

By using tensorflow, conv layer, pooling layer, activation, and fully connected layer are implemented.
Then compares the calculated logit with the actual label and optimizes it to minimize the difference.

- ### Train the model and validate & test it **(Our goal is to achieve validation accuracy of over 93%)**

The model is trained by passing the input sign through a convolution neural network and minimizing the difference between the predicted value and the actual value. The result is below.

![screenshot from 2018-05-29 23-34-37](https://user-images.githubusercontent.com/35591154/40666059-d243d686-6399-11e8-8fe6-0dd0b5b731d1.png)


- ### Test a Model on New Images

Apply the six German traffic signs received from the Internet to the learned models to ensure that the learned models correctly distinguish traffic signs.

![screenshot from 2018-05-29 23-35-29](https://user-images.githubusercontent.com/35591154/40666109-ef659a7e-6399-11e8-86c8-f006646c8831.png)



----
## Configuration

- ### Traffic_Sign_Classifier.ipynb

contains a complete code to implement the actual project
In addition, the results and descriptions of each process have been added to confirm the entire process

- ### Writeup.md

It is a file that describes the important process in detail

- ### Traffic_Sign_Classifier.html

converts ipynb file to html

- ### New_images

contains new images obtained from internet

- ### signnames.csv

contains what the German traffic sign label means.
