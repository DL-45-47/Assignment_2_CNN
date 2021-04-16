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
