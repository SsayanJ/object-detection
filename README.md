# object-detection
Use TensorFlow pretrain models for new object recognition (with additional data)  

## Data preparation
Additional data needs to be labelled. The below tool can be use:
[Labelling tool (LabelImg)](https://tzutalin.github.io/labelImg/)  
Once the data is labelled, it needs to be converted to the proper input tfrecord format for the model training (.record).
This can be done using the `generate_tfrecord.py` from this repository ([link](https://gist.githubusercontent.com/yasserius/ef9eb79c3f2f516ed1e4f793150d6f76/raw/20cee1a342d79e24b649a7b3dbc9500be832ce6f/tfrecord_generator.py)).  
It is also copied in this repository but it is not my code.

The notebook is based on this [Colab Notebook](https://colab.research.google.com/drive/1Dn3bgYkialkPXImM1XWaYqjgVNTGI9Fn?usp=sharing#scrollTo=IQFtz_n0ohgB) that I simply adapted to my use case and where I added the inference part from Gilbert Tanner's repository (see in the sources).

## Sources:  
1 - Main Colab Notebook:
- [Object Detection TensorFlow2 - use pre-trained model for new object detection](https://colab.research.google.com/drive/1Dn3bgYkialkPXImM1XWaYqjgVNTGI9Fn?usp=sharing#scrollTo=IQFtz_n0ohgB)  

2 - Gilbert Tanner tutorial:
- [Youtube tutorial](https://www.youtube.com/watch?v=cvyDYdI2nEI&ab_channel=GilbertTanner)
- [Written tutorial](https://gilberttanner.com/blog/tensorflow-object-detection-with-tensorflow-2-creating-a-custom-model)
- [Github repo](https://github.com/TannerGilbert/Tensorflow-Object-Detection-API-Train-Model)  

3 - Available Tensorflow trained models:
- [Tensorflow2 Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md)
