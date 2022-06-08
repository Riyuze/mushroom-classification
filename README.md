
# Mushroom Classification

An image classification project which detects different kinds of mushroom species using **Keras** and **Tensorflow**.  Image Classification is a Machine Learning module that trains itself from an existing dataset of multiclass images and develops a model for future prediction of similar images not encountered during training. Developed using Convolutional Neural Network (CNN).

Tensorflow: https://www.tensorflow.org/

Keras: https://keras.io/




## Convolutional Neural Network (CNN)

A convolutional neural network (CNN) is a type of artificial neural network used in image recognition and processing that is specifically designed to process pixel data.

More information can be found here: https://www.analyticsvidhya.com/blog/2021/06/image-processing-using-cnn-a-beginners-guide/


## Pre-requisites

Create a python virtual environment using:
```bash
python -m venv /path/to/new/virtual/environment
```

Then, fork the code and place it in the root folder.

Next, activate the virtual environment using (Windows):
```bash
Scripts/activate
```

Check https://docs.python.org/3/library/venv.html for more details.

After the virtual environment is activated, install the dependencies needed using:

```bash
pip install -r requirements.txt
```
    
## Dataset

Download the dataset you want to train the model with, for this project I placed each of the mushroom species inside a subfolder. This will enable the use of: https://www.tensorflow.org/api_docs/python/tf/keras/utils/image_dataset_from_directory
and labels the data according to the names on the subfolders.

The dataset I used was a custom dataset I made by downloading each species of the
mushrooms from: www.gbif.org

In total there were:
| Datasets | Number of Images |
| ----------- | ----------- |
| Training Set | 2720 |
| Validation Set | 680 |
| Total | 3400 |

80% of the dataset was used for the Training Set and the 20% for the Validation Set.

![Images and Labels](https://github.com/Riyuze/mushroom-classification/blob/main/image-labels.png)



## Experiments

### Normalization
For normalization, I rescaled the image's RGB values from [0, 255] to [0, 1] using:
https://www.tensorflow.org/api_docs/python/tf/keras/layers/Rescaling

### Data Augmentation
I augmented the data using:
- https://www.tensorflow.org/api_docs/python/tf/keras/layers/RandomFlip
- https://www.tensorflow.org/api_docs/python/tf/keras/layers/RandomRotation
- https://www.tensorflow.org/api_docs/python/tf/keras/layers/RandomZoom

Which basically will randomly **rotate**, **flip**, and **zoom** the images when training.

![Augmented Data](https://github.com/Riyuze/mushroom-classification/blob/main/data-augmentation.png)


## Results
In this project there are 2 models, one used basic **Sequential** layers and the
other using a pre-trained **ResNet50** model.

More about **ResNet50** here:
https://www.tensorflow.org/api_docs/python/tf/keras/applications/resnet50

Here is the result for the basic **Sequential** model:

![Sequential](https://github.com/Riyuze/mushroom-classification/blob/main/normal-result.jpeg)

Here is the result for the **ResNet50** model:

![ResNet50](https://github.com/Riyuze/mushroom-classification/blob/main/resnet50-result.png)

As you can see the ResNet50 model has far greater validation accuracy and smaller loss.

## Source
More information about image classification in Tensorflow can be found here:
https://www.tensorflow.org/tutorials/images/classification



