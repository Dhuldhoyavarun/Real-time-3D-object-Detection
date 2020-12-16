# Dlproject


## DEEP LEARNING - IMAGE CAPTIONING: A COMPARATIVE STUDY
To be Filled 

## Study 1 : Attention Model + ResNet50  
##### Model Description:

| Attention Mechanism | Vocabulary(Unique Words) |Number of Images|Training Epochs|Captions per image|Total Datapoints|Training Batch Size|
|-------------------- | -------------------------|----------------|---------------|------------------|----------------|-------------------|        
|  Bahdanau Attention | 7,000                    | 6,000          | 30            |5                 |      30,000    | 64                |

View Detailed Results     |  View Detailed Epoch Results
:-------------------------:|:-------------------------:
[Click To View](https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/attentionResNetResults.pdf)  |  [Click To View]()


##### EXAMPLE: GOOD PREDICTION RESULT
 <p align="center">
  <img height="400" width="500" src="https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/good/good2.png">
</p>

##### BLEU SCORE, GLEU SCORE and WER (Word Error Rate) metric comparison between sentences:
 <p align="center">
  <img width="1040" height="180" src="https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/good/print-goodres.png">
</p>

##### EXAMPLE: FAIR PREDICTION RESULT
 <p align="center">
  <img height="225" width="630" src="https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/fair/fair2.png">
</p>

##### BLEU SCORE, GLEU SCORE and WER (Word Error Rate) metric comparison between sentences:
 <p align="center">
  <img width="950" height="210" src="https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/fair/fair3-final.png">
</p>

##### EXAMPLE: BAD PREDICTION RESULT
 <p align="center">
  <img height="250" width="700" src="https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/bad/bad1.png">
</p>

##### BLEU SCORE, GLEU SCORE and WER (Word Error Rate) metric comparison between sentences:
 <p align="center">
  <img width="900" height="180" src="https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%2BResNet%20Results/bad/badRes-final.png">
</p>

##### CUMMULATIVE : BLEU SCORE, GLEU SCORE and WER (Word Error Rate) metric scores for model:

WER- WORD ERROR RATE       |  PREDICTIONS
:-------------------------:|:-------------------------:
![](https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Images/final2.png)  |  ![](https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Images/predictions2.png)

View Detailed Epoch Results     |  View Folder Containing Image Results
:-------------------------:|:-------------------------:
[Click To View](https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/blob/main/Attention%20Results/attention-model2/epochs/attention-model-3.pdf)  |  [Click To View](https://github.com/HemanthTejaY/Image-Captioning-A-Comparative-Study/tree/main/Attention%20Results/attention-model2)


## COLOR CODE OF OBJECTS

* Actual Image - White
* Car - Red
* Tram- Cyan
* Cyclist - Pink
* Truck - Blue
* Pedastrian - Yellow

## OBSERVATIONS
----# Observations:

Initally we had faced an overfitting issue while running at 100 epochs with batch size of 12, where its showing false positives. Later when we adjusted it to 62 epochs and 32 batch size, the place where we got the first lower curve served our purpose way better than previous configuration of hyper parameters. 




## REFERENCES


