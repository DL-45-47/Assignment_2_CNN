# Assignment 2 - Convolution Neural Network

### Files :
* **DLA2PartA.ipynb** - Trained CNN model from scratch executable code with Sweep functionality
* **TestAccuracyA2PartA.ipynb** - Using Trained CNN model to find accuracy on test dataset
* **DLA2PartB.ipynb** - Pre-Trained CNN model executable code with Sweep functionality
* **MakeYolov3Model.ipynb** - Training YOLOv3 executable code
* **ObjectDetection.ipynb** - Executable code to convert video to frames, detect required objects using YOLOv3 and convert detection frames to video
* **Resize_images.ipynb** - Executable code to resize given dataset images to (500X500X3) dimension and store
* **Data_Augumentation.ipynb** - Executable code to apply Data Augmentation on given dataset images and store
* **README.md** - Brief description about project

### Quick Run :
* Firstly execute *sweep_config* and *wandb.sweep* modules that initialize sweep with parameters and return sweep id.
* Then execute *wandb.agent* that train model with various combination of parameters.<br/>
**Note -** *It is suggested to pre-run all modules i.e. import, algorithms and supportive functionalities.*

### Key Points for Execution :
* It is a modular code in jupyter notebook format.
* One who needs to run this notebook should have a wandb login which is needed for execution of the code.
* Code is structured based on sweep functionality. There are two important sweep functions -
  * wandb.sweep - to initiate sweep with config parameters and project name and returns sweep id
  * wandb.agent - take parameters as sweep id and function name to be executed in loop with different combinations of parameters.
* It is preferred to execute all algorithm at begin as well, since sweep function randomly choose algorithms for execution.

### Part A - Train a CNN model from scratch
* Used train data and validation data to train model from given nature_12K dataset
* CNN model contains 5 convolution layers, a dense layer and classification layer along with Dropout, Batch Normalization and Max Pooling applied on suitable layers.
* Following hyperparameters were used -
  * epochs : 5, 10, 15, 20
  * Initial number of filters : 16, 32, 64
  * filter organisation : 2, 1, 0.5
  * data augmentation : False, True, True
  * batch normalization : False, True, True
  * kernel size : 3, 5, 7
  * neuron in dense layer : 32, 64, 128, 256
  * dropout : 0.2, 0.3
  * weight decay : 1e-1, 1e-2, 1e-3
  * number of convolution layers : 4, 5, 6, 7
  * batch size : 16, 32, 64
* Feature map of Convolution Layer was visualized and accuracy of trained model was evaluated based on test dataset.

### Part B - Fine tuning Pre-trained CNN model
* Used train data and validation data to fine tune with the help of given nature_12K dataset
* Following Pre-trained CNN models were used -
  * VGG16
  * InceptionV3
  * InceptionResNetV2
  * ResNet50
  * Xception
* Weight before fine tuning were initialized to weights returned by pre-trained model before fine tuning.
* Following hyperparameters were used -
  * epochs : 5, 7, 9, 10, 11
  * weight decay : 1e-1, 1e-2, 1e-3, 0.00099, 0.00111
  * pooling : 'max', 'avg'
  * data augmentation : False, True, True
  * pre trained model : 'VGG16', 'InceptionV3', 'InceptionResNetV2', 'ResNet50', 'Xception'
  * batch size : 8, 16, 32

### Part C - Object Detection using YOLOv3
* Approach -
  * Trained model on YOLOv3 architecture
  * Converted video to frames
  * Applied model to detect motor vehicles in video frames and box them
  * Convert boxed frames to video
* YouTube video link - https://youtu.be/kneV3Z2fcN4
