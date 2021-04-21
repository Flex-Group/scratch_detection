### scratch_detection
Mask_rcnn model trained to detect external scratches on the body of vehicles

How to train the Mask RCNN model on a GPU (Google colab or AWS):

### First, mount the google drive:

$from google.colab import drive
$drive.mount('/content/gdrive')

### Clone the repo that has the Mask-RCNN model and the dataset that will be used for training:

$git clone https://github.com/Flex-Group/scratch_detection

### Install Tensorflow and Keras:

$pip install tensorflow==1.15.0\\
$pip install keras==2.2.5

### Install the required packages using the requirements.txt file:

$pip install -r scratch_detection/requirements.txt

### Unzip the mrcnn folder, scratch_dataset folder and logs folder respectively as follows:
### -The mrcnn folder contains the python scripts for the Mask-RCNN model
### -The scratch_dataset contains the prepared (annotated) images coupled with the json format file that will be used for training the model.
### -The logs folder is where the weights of the model will be saved at each epoch. No need to create the folder since it can be created by the python script.

$unzip scratch_detection/mrcnn.zip
$unzip scratch_detection/scratch_dataset.zip
$unzip scratch_detection/logs.zip

### Copy or Move the unzipped folders back into the main folder, which is the scratch_detection folder:

$cp mrcnn -r scratch_detection/
$cp scratch_dataset -r scratch_detection
$cp logs -r scratch_detection

### Train the Mask RCNN model using the prepared scratch_dataset as follows

$python3 /content/scratch_detection/scratch_model.py train --dataset=/content/scratch_detection/scratch_dataset --weight=coco

### Note that, once the model training is completed, the weights of the model will be saved in the logs directory. 
### These weights will be used to test and apply the model.


