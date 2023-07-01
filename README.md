# Automatic-number-plate-recognition-in-real-time

## data
### [data](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbTE0Sm5ZY0hsWHJULUIzZ3d6TGNuQlphdFJyZ3xBQ3Jtc0tsMWlnR3hEVG1MX0ZiX3F0UXF1Nlp0Mm96N3hqV0ZlNlpFd1g1ZTZuVHVUNUU2aGxtQnVSaFU4eG5XQmVWalBXeWJ4cnpJbTI2YzhyeURoTEpMZUpvejBpV2hibklfek9fU3FmcE90Q0tUd2M3Q0Nhdw&q=https%3A%2F%2Funiverse.roboflow.com%2Froboflow-universe-projects%2Flicense-plate-recognition-rxg4e%2Fdataset%2F4&v=SAm5bYjeu_k)

## video-for-test
### [video](https://drive.google.com/file/d/1YmHTElM6rh5uBpvaoUYpYTHK2odJkoM6/view)


### install method
```bash
    pip intall -r requirements.txt 
```
### install method
```bash
    pip install roboflow
```

### download dataset and labeling dataset
```python
    from roboflow import Roboflow

    rf = Roboflow(api_key="your_api_key")
    project = rf.workspace("roboflow-universe-projects").project("license-plate-recognition-rxg4e")
    dataset = project.version(4).download("yolov8")
```
### start train data 
```bash
    !yolo task=detect mode=train model=yolov8n.pt data='/content/License-Plate-Recognition/data.yaml' epochs=25 imgsz=640
```

### how use it ?
1. **Prepare your data.** You need to have a dataset of images or videos that you want to train or test the model on. The dataset should be annotated, which means that each image or video should have bounding boxes around the objects that you want to detect. You can use the LabelImg: https://github.com/tzutalin/labelImg tool to annotate your data.
2. **Create a dataset configuration file.** This file tells the YOLOv8 training code how to load and process your dataset. You can find an example of a dataset configuration file here: https://github.com/ultralytics/yolov3/blob/master/data/coco.yaml
3. **Install YOLOv8.** You can install YOLOv8 using pip:

```
pip install yolov8
```

4. **Train the model.** You can train the model using the `yolo` command line utility. The following command will train a YOLOv8 model on a dataset of images called `my_dataset`:

```
yolo train --data my_dataset --weights yolov8-s.weights --epochs 100
```

The `--weights` argument specifies the path to a pre-trained YOLOv8 model. If you don't specify this argument, the model will be randomly initialized. The `--epochs` argument specifies the number of training epochs.

5. **Evaluate the model.** Once the model is trained, you can evaluate it on a new dataset of images or videos. The following command will evaluate the model on a dataset of images called `my_dataset`:

```
yolo evaluate --data my_dataset --weights yolov8-s.weights
```

The output of the `evaluate` command will show you the accuracy of the model on the test dataset.

Here are some tips for training a YOLOv8 dataset:

* Use a large dataset of images or videos. The more data you have, the better the model will be.
* Make sure your dataset is well-annotated. The bounding boxes should be accurate and consistent.
* Use a powerful GPU. Training a YOLOv8 model can be computationally expensive, so you will need a powerful GPU to train the model quickly.
* Be patient. Training a YOLOv8 model can take a long time, so be patient and let the model train until it converges.


## SORT
=====

A simple online and realtime tracking algorithm for 2D multiple object tracking in video sequences.
See an example [video here](https://alex.bewley.ai/misc/SORT-MOT17-06-FRCNN.webm).

By Alex Bewley  

### Introduction

SORT is a barebones implementation of a visual multiple object tracking framework based on rudimentary data association and state estimation techniques. It is designed for online tracking applications where only past and current frames are available and the method produces object identities on the fly. While this minimalistic tracker doesn't handle occlusion or re-entering objects its purpose is to serve as a baseline and testbed for the development of future trackers.

SORT was initially described in [this paper](http://arxiv.org/abs/1602.00763). At the time of the initial publication, SORT was ranked the best *open source* multiple object tracker on the [MOT benchmark](https://motchallenge.net/results/2D_MOT_2015/).

**Note:** A significant proportion of SORT's accuracy is attributed to the detections.
For your convenience, this repo also contains *Faster* RCNN detections for the MOT benchmark sequences in the [benchmark format](https://motchallenge.net/instructions/). To run the detector yourself please see the original [*Faster* RCNN project](https://github.com/ShaoqingRen/faster_rcnn) or the python reimplementation of [py-faster-rcnn](https://github.com/rbgirshick/py-faster-rcnn) by Ross Girshick.

#### from here
[here](https://github.com/abewley/sort.git)