# Dlproject


## DEEP LEARNING - REAL-TIME 3D OBJECT DETECTION
3D object detection has become inevitable for day-to-day applications be it autonomous driving or constructing images or even for augmented reality since it directly links to environmental understanding and therefore builds the base for prediction and motion planning. But, in the case of real-time 3D object detection, we need to deal with highly sparse data considering its usage amongst real-life objects. In those cases, it is extremely inefficient to process data in general methods of detection and also to reduce the noise during this process is tiresome.

##### Model Description:

| Model Name          | Training Set             | Evaluation set |Training Epochs|Training Batch Size|
|-------------------- | -------------------------|----------------|---------------|-------------------|        
| Complex YOLO Low accuracy        |      6000                | 1,500          | 62            | 32                |
| Complex YOLO High accuracy       |      6000                | 1,500          | 100           | 12                |

View Detailed Results     |  View Detailed Epoch Results
:-------------------------:|:-------------------------:
[62 Epochs](https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/loss_vs_epoch.png)  |  [100 Epochs](https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/loss%20vs%20epoch%202.png)


## OBSERVATIONS

Initally we had faced an overfitting issue while running at 100 epochs with batch size of 12, where its showing false positives. Later when we adjusted it to 62 epochs and 32 batch size, the place where we got the first lower curve served our purpose way better than previous configuration of hyper parameters. 


##### EXAMPLE: GOOD PREDICTION RESULT
 <p align="center">
  <img height="400" width="500" src="https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/eval_bv006036-good.png">
</p>

##### EXAMPLE: FAIR PREDICTION RESULT
 <p align="center">
  <img height="225" width="630" src="https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/model_fair.png">
</p>

##### EXAMPLE: BAD PREDICTION RESULT
 <p align="center">
  <img height="250" width="700" src="https://github.com/Dhuldhoyavarun/Dlproject/blob/main/results/model_bad.png">
</p>


## COLOR CODE OF OBJECTS

* Actual Image - White
* Car - Red
* Tram- Cyan
* Cyclist - Pink
* Truck - Blue
* Pedastrian - Yellow





## REFERENCES


