**This is the project website for CS 766 Computer Vision in the University of Wisconsin-Madison**
## Documents
[Proposal](https://github.com/arrow789/CS766_Project/files/8614111/CS766.Project.Proposal.pdf)

[MidTerm Report](https://github.com/arrow789/CS766_Project/files/8614186/MidTerm.Report.pdf)

[Final Presentation](https://github.com/arrow789/CS766_Project/files/8614190/Presentation.pdf)

## Introduction
Emotion recognition has attracted major attention in numerous fields because of its relevant applications in the contemporary world. Marketing, psychology, surveillance, and entertainment are some examples. 

It is possible to recognize emotion in several ways, such as facial expression, body language or speaking tones. Facial Expression Recognition (FER) is an important visual recognition technology to detect emotions given input to the intelligent system. There are many applications in multiple domains as below.

•Human–Computer Interaction
•Virtual Reality 
•Augmented Reality 
•Advanced Driver Assistance Systems 
•Education
•Entertainment

## Goals
This project focuses on the state-of-art FER methods and reimplements FER algorithms (including Conventional and Deep Learning-based approaches). Two groups will be tested and compared on several datasets(In-the-Lab/ In-the-Wild). Defects of current methods and future works will be pointed out.

## Why FER is important?
FER in the human-computer interactive system is one of the challenging research topics in the field of artificial intelligence which has drawn plenty of attention in recent years. However, it is difficult to achieve natural and harmonious emotional interaction with traditional interaction methods such as keyboard, mouse, screen, and pattern, which is far from meeting the requirements for artificial intelligence. 
Human expression is the most important carrier of inspirational perception and the most direct and obvious way of expressing emotions. And Facial expression is arguably the most natural, powerful, and immediate signal to communicate emotional states and intentions. Thus, FER has important theoretical significance for improving the emotional interaction ability of computers.

## State-of-Art
There are many approaches in different areas to achieve FER. 

For example, we can use RF signals to measure heart beats and get the emotions. We can use the Thermals measurement to get blood flow on face to get the emotions.

| ![The Procedure of RF Signals Detecting Emotion](https://user-images.githubusercontent.com/46728665/166586964-b8583cf9-b2da-42a8-a776-172e10028b03.png)
|:--:| 
| *The Procedure of RF Signals Detecting Emotion* |

| ![image](https://user-images.githubusercontent.com/46728665/166587223-af64c7bc-e513-4e95-9a6b-fa33e4f00588.png)
|:--:| 
| *RF Signal Classification* |

In the computer vision areas, work [1] applies the HOG to encode these facial components as features. A linear SVM is then trained to perform the facial expression classification. Paper [2] proposes es-LBP (expression-specific LBP) which could better capture the local information of faces on important fiducial points. However, it has the disadvantage of being sensitive to noise. Due to an increase in the ready availability of computational power and increasingly large training databases to work with, the machine learning technique of neural networks has seen a resurgence in popularity. Work [3] presents a new deep neural network architecture for FER which increased classification accuracy on both subject independent and cross-database evaluation scenarios. The addition of  Inception layers increases the depth and width of the network while keeping the computational budget constant. Paper [4] instead of using the whole face region, three kinds of active regions are applied to classify facial expression through a decision-level fusion strategy. Work [5] proposes a deep convolutional fusion network, which addresses the FER task through discriminative spatial features learning and temporal dependencies accumulating.

| ![image](https://user-images.githubusercontent.com/46728665/166588429-30fa8c99-8f81-4ae0-b7b4-797b3e55c21f.png)
|:--:| 
| *Deep Convolutional Fusion Network* |

## Types of Emotions
Types of emotions, there are basic emotions[6], which include happiness, surprise, sadness, anger, disgust, and fear. Compound emotions are combinations of two basic emotions. 22 emotions are introduced in [7], including 7 basic emotions (6 basic emotions and 1 neutral), 12 compound emotions expressed commonly by humans, and 3 additional emotions (Awed, Appalled, and Hatred). Microexpressions [8] represent more spontaneous and subtle facial movements that occur involuntarily. They tend to reveal the true and potential expressions of a person for a limited time. The duration of the micro expression is very short and lasts for only 1/25 to 1/3 s. Studies on micro expressions are often applied in psychology and police investigations.
In this project, we will focus on 7 emotions as below.

| ![image](https://user-images.githubusercontent.com/46728665/166609520-0869e151-9cc0-4218-b0e0-da6fda2c9070.png)
|:--:| 
| *7 Emotions* |

## FER Datasets
FER datasets can be divided into two different parts, including the in-the-lab dataset and the in-the-wild dataset. 
CK+ is one of the in-the-lab datasets, the facial expressions were recorded from frontal camera-view points, and their peaks were carefully annotated and validated in terms of 30 action units. AU is one of two models to catalog the emotions, we will introduce them later. ([CK+ Download](https://github.com/spenceryee/CS229))

AffectNet is the largest dataset of facial expressions in the wild publicly available. It contains more than one million images retrieved from the Internet using emotion keywords from different languages, where half of them were manually annotated by human experts using 8 discrete emotions, arousal and valence levels. In addition to its heterogeneity, the heavily imbalanced label distribution (e.g., contempt constitutes only 1% of the annotated images) and the strong baselines pose a real challenge for the affective computing community. ([AffectNet Download](http://mohammadmahoor.com/affectnet/))

FER+ (Barsoum et al. 2016) derives from the reannotation of the Facial Expression Recognition 2013 (FER- 2013) dataset (Goodfellow et al. 2015) due to the originally high degree of noise presented in the annotations. FER-2013 was created by querying facial images from Google’s image search engine using 184 emotion keywords. Each of the 35,887 facial images was then re-labeled by 10 annotators using crowd-sourcing, and the contempt category was added to the dataset as one of the possible 8 emotion labels. ([FER+ Download](https://github.com/Microsoft/FERPlus))

| ![image](https://user-images.githubusercontent.com/46728665/166611859-1020a308-1b4b-4750-b8e7-b6881930acbd.png)
|:--:| 
| *Comparison between Three Datasets* |

## Conventional Methods
A notable characteristic of the conventional FER approach is that it is highly dependent on manual feature engineering. The researchers need to pre-process the image and select the appropriate feature extraction and classification method for the target dataset.

The conventional FER procedure can be divided into three major steps: image pre-processing, feature extraction, and expression classification.

| ![image](https://user-images.githubusercontent.com/46728665/166613834-ca82ae23-ea5d-483e-8798-41b0d424c248.png)
|:--:| 
| *Three Steps for Conventional FER* |

Image pre-processing is to eliminate irrelevant information of input images, like the complex backgrounds, light intensity, and occlusion. Also, different sizes of datasets, and different camera hardware can cause data diversity. We need to do the pre-processing to enhance the detection ability of relevant information. Feature extraction is a process to extract useful data or information from the image, eg, values, vectors, and symbols. We’ve learned lots of feature extraction methods this semester. Another key to affecting the expression recognition rate is how to select the appropriate classifier that can successfully predict the face expressions. There are many choices here.

Here is one example. This paper begins with face detection using the Viola-Jones face detector. This detector searches the Haar-like features. Once the face region is acquired, we can extract the brows, eyes, nose, and mouth from the face. Facial expressions result from muscle movements and these movements could be regarded as a kind of deformation. And Histogram of the Oriented Gradient is pretty sensitive to these object deformations. We use HOG to encode the components. The classifier is Support Vector Machines. Again, we can change this part to KNN or linear regression. We can also change the HOG to Gabor feature. It depends on which types of datasets you are using. 

| ![image](https://user-images.githubusercontent.com/46728665/166614855-6ff2a686-33c5-4420-bd6b-fe58bb69cf15.png)
|:--:| 
| *Example of Conventional FER Methods* |

**Here is the result. CK+ and JAFFE are in the lab datasets. It reaches out to 88.7% accuracy on CK+ and 94.3% on JAFFE.**

**Since Viola-Jones was designed for frontal faces, not for faces looking sideways, upwards, or downwards. So I change the Viola-Jones with dlib, which is feature point tracking with 68 point facial landmarks. So on the in-the-wild dataset, I got 50% accuracy on 7 emotions, and 60% accuracy on 5 emotions.**

## Deep Neural Network
The next method is the deep neural network. So, why do we use the Neurol Network in FER? Neural networks can automatically learn features from data, so hand-feature engineering was left out in the pipeline. Besides that, feature learning allows deep networks to learn a broader range of facial features. In visual perceptual tasks, certain features previously learned can be transferred among related tasks to save time.

The reason I choose Ensemble methods in neural networks is that I think the result of the emotion classifier cannot output just one emotion, there might be some compound emotion. As for the benefits, a well-trained ensemble can reduce the remaining residual generalization error, which results in predictions being more accurate than any single model in the ensemble. But it requires high computational power, there are many solutions for this problem. To make this training-intensive technology accessible to everyone. Here are two solutions. One is rather than using the whole dataset for training, the ensemble method is trained on the most informative samples that maximize learning. The second one is that input space is decomposed into multiple regions, and each region is used to train one convolutional neural network of the ensemble.

Here is another example. An Ensembles with Shared Representation consists of two building blocks. The base of the network (gray blocks in Figure) is an array of convolutional layers for low- and middle-level feature learning. The first part is responsible for the reduction of redundancy, training, and inference time. The low-level features learned by them are shared with the ensemble of convolutional branches. The second part is independent convolutional branches (purple blocks) that constitute the ensemble. It characterizes the explicit part and carries the diversity of the ensemble.

| ![image](https://user-images.githubusercontent.com/46728665/166617351-1d0789e4-8132-4655-9a0a-bb4184d631c3.png)
|:--:| 
| *ESR Network* |

The level to start the ensemble of branches plays an important role in the computational load and generalization power as well as for redundancy and diversity starting branching too early (level 1) may result in high redundancy of low-level facial features where all branches have to learn skin textures and so forth. Branching too late may drastically decrease diversity in the ensemble where features from the shared layers no longer correspond to spatial facial features

Tractional Ensemble needs more training epochs than ESR to learn informative facial features. For example, ESR learned, after the first update that, the region around the mouth is relevant for recognizing happy facial expressions. And it took the Traditional Ensemble of 50 epochs to learn. For diversity analysis of ESR, the Facial Action Coding System (one model for dividing emotions) indicates that happy mainly consists of the raising of cheeks(AU-6) and mouths(AU-12), which can be shown on ESR Branch 2 (After Training). Fear consists of raising the inner brow(AU-1) and stretching of lip(AU-20) which can be shown on ESR Branch 2 (Epoch 50)

| ![image](https://user-images.githubusercontent.com/46728665/166618266-6250fea2-1059-4134-9516-6edbd6623706.png)
|:--:| 
| *TE vs ESR* |

**Here are the results, in the CK+, it achieves 89.4% accuracy, with fewer parameters to train compared with Traditional Emblems. And on the in-the-wild dataset, it achieves 59.3% on AffectNet and 87.15% in FER+.**

| ![image](https://user-images.githubusercontent.com/46728665/166618663-39cc7e21-084a-4d4d-9eb4-b3e1141e095e.png)
|:--:| 
| *ESR Accuracy on CK+* |

## Demo
This is another model for dividing emotions. We use arousal and valence 2D coordinates to divide emotions based on the whether emotions are Active/Passive and Positive/Negative.

<img src="https://user-images.githubusercontent.com/46728665/166618921-405a838a-6bed-4f35-99cf-9ab5cc56aec4.png" width=50% height=50%>

Below is the demo of ESR on a video.

<video src="https://user-images.githubusercontent.com/46728665/166618804-a565e8dd-f2b1-4dbe-847e-aff83cac0b56.mov" controls="controls" style="max-width: 730px;">
</video>

# Defects & Future Work
Both conventional and deep learning methods still have low accuracy on the large in-the-wild dataset. There is also pressure on high-volume data processing.
Future work includes the Multi-Model Affect Recognition, including Sound, Face Depth Map, and IR images. Also, we need to consider the vision of privacy.

