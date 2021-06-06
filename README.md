# object-detection
Use TensorFlow pretrain models for new object recognition (with additional data)  

## Data preparation
Additional data needs to be labelled. The below tool can be use:
[Labelling tool (LabelImg)](https://tzutalin.github.io/labelImg/)  
Once the data is labelled, it needs to be converted to the proper input for the model training (.tfrecord).
This can be done using the 2 files available in this repository `xml_to_csv.py` and `generate_tfrecord.py`.  
First generate the csv files with this command ```python xml_to_csv.py``` from the folder where the images are.  
**Note**: it is expected that there is an *images* folder in the folder where this script is exectuted.  
<br>  

The ```generate_tfrecord.py``` file needs to be slightly modified to suit our specific new classes:
```python
def class_text_to_int(row_label):
    if row_label == 'green_cup':
        return 0
    elif row_label == 'red_cup':
        return 1
    else:
        return None
```
Then generate the record file with the below commands.
```
python generate_tfrecord.py --csv_input=images/train_labels.csv --image_dir=images/train --output_path=train.record
python generate_tfrecord.py --csv_input=images/test_labels.csv --image_dir=images/test --output_path=test.record
```  




More details on the written tutorial in sources.

## Sources:  
1 - Gilbert Tanner tutorial:
- [Youtube tutorial](https://www.youtube.com/watch?v=cvyDYdI2nEI&ab_channel=GilbertTanner)
- [Written tutorial](https://gilberttanner.com/blog/tensorflow-object-detection-with-tensorflow-2-creating-a-custom-model)
- [Github repo](https://github.com/TannerGilbert/Tensorflow-Object-Detection-API-Train-Model)  

2 - Available Tensorflow trained models:
- [Tensorflow2 Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md)
