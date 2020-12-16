## DEEP LEARNING - REAL-TIME 3D OBJECT DETECTION
3D object detection has become inevitable for day-to-day applications be it autonomous driving or constructing images or even for augmented reality since it directly links to environmental understanding and therefore builds the base for prediction and motion planning. But, in the case of real-time 3D object detection, we need to deal with highly sparse data considering its usage amongst real-life objects. In those cases, it is extremely inefficient to process data in general methods of detection and also to reduce the noise during this process is tiresome.

## MODEL:

### PREPROCESSING USING LIDAR POINT CLOUD REPRESENTATION
We project the point cloud to create a bird’s eye view grid map. We create two grid maps from the projection of the point cloud. The first feature map contains the maximum height, where each grid cell (pixel) value represents the height of the highest point associated with that cell. The second grid map represent the density of points. Which means, the more points are associated with a grid cell, the higher its value would be. The density is calculated using the following equation:
$min(1.0,log(N + 1)/log(64) )$, Where N is the number of points in each grid cell.

### COMPLEX-YOLO
Complex-YOLO is a 3d version of the YOLOv2, one of the fastest state of the art object detectors. The Complex-YOLO network takes a birds-eye-view RGB-map as input. It uses a simplified YOLOv2  CNN architecture, extended by a complex angle regression and E-RPN, to detect accurate multi-class oriented 3D objects while still operating in real-time. 

Complex YOLO converts the orientation vector to real and imaginary values. The problem with this is that the regression does not guarantee, or preserve any type of correlation between the two components of the angle.

## ARCHITECTURE
We design a new CNN architecture base on YOLOv2 to detect 3D objects in real-time, called 3DNet. It has 18 convolutional layers and 5 maxpooling layers. After each convolutional layer, there is a LReLU and BN layer, except in the last layer.

![Architecture Diagram](https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/complex%20yolo%20pipeline.png)

## TRAINING AND HYPER PARAMETERS
We used the following while training the model.
* We trained the network for 100 epochs, with a batch size of 32.
* Our learning rate is 0.001.
* We wrote a function Region Loss to calculate the training loss of the model for 7 classes and we used 5 anchors.
* To classify the objects, we used a threshold of 0.7 for cars and 0.5 for rest of the classes

## RESULTS

| Model Name          | Training Set             | Evaluation set |Training Epochs|Training Batch Size|
|-------------------- | -------------------------|----------------|---------------|-------------------|        
| Complex YOLO Low accuracy  |      6000         | 1,500          | 62            | 32                |
| Complex YOLO High accuracy |      6000         | 1,500          | 100           | 12                |

![Comparison](https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/comparison.png)

View Detailed Results     |  View Detailed Epoch Results
:-------------------------:|:-------------------------:
![62 Epochs](https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/loss_vs_epoch.png)  |  ![100 Epochs](https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/loss%20vs%20epoch%202.png)


## OBSERVATIONS

Initally we had faced an overfitting issue while running at 100 epochs with batch size of 12, where its showing false positives. Later when we adjusted it to 62 epochs and 32 batch size, the place where we got the first lower curve served our purpose way better than previous configuration of hyper parameters. 


##### EXAMPLE: GOOD PREDICTION RESULT
This Model prediction is detecting all the objects that are labelled and also some objects that are present but are not labelled in actual data. This model extrapolated in detecting beyond actual data much accurately. This is an example of real-world application of the model where we can't have always efficient labelled data as inputs. That's where we can see here remaining 2 cars, that weren't labelled using white boxes are still found accurately using these model predictions.
 <p align="center">
  <img height="225" width="630" src="https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/eval_bv006036-good.png">
</p>

##### EXAMPLE: FAIR PREDICTION RESULT
This Modelling is making sure that objects  within visible range are detected properly, but hidden objects are not predicted properly. 
 <p align="center">
  <img height="225" width="630" src="https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/model_fair.png">
</p>

##### EXAMPLE: BAD PREDICTION RESULT
This Model prediction is unable to match with actual labelling. This is missing a couple of detections which are supposed to be recognized.   

 <p align="center">
  <img height="225" width="630" src="https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/model_bad.png">
</p>


## COLOR CODE OF OBJECTS

* Actual Image - White
* Car - Red
* Tram- Cyan
* Cyclist - Pink
* Truck - Blue
* Pedastrian - Yellow

## REFERENCES
[Complex-YOLO: An Euler-Region-Proposal for
Real-time 3D Object Detection on Point Clouds](https://arxiv.org/pdf/1803.06199.pdf)
  
[LO3D: End-to-end real-time 3D Oriented Object Bounding Box Detection from LiDAR Point Cloud](https://arxiv.org/pdf/1808.02350v1.pdf)  

[Expandable YOLO: 3D Object Detection from RGB-D Images](https://arxiv.org/ftp/arxiv/papers/2006/2006.14837.pdf)

[VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection](https://arxiv.org/pdf/1711.06396.pdf)



