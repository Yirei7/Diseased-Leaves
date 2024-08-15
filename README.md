# Project Name

 This project allows the user to identify how much a leaf is diseased. It is be useful for avoiding inedible leaf vegetables.

![add image descrition here](direct image link here)
[Insert HEALTHY Image HERE]
![image](https://github.com/user-attachments/assets/479e4d28-492d-48f6-b1db-ea7ea09b9222)

## The Algorithm

Add an explanation of the algorithm and how it works. Make sure to include details about how the code works, what it depends on, and any other relevant info. Add images or other descriptions for your project here. 

This project was created using the Jetson Nano. The model is essentially a retrained resnet-18, trained on a dataset containing various leaves, each labeled with their corresponding class (either blight or healthy). When the model is executed, it uses the imagenet.py program along with the trained model to classify the leaf's health from a given image.

![image](https://github.com/user-attachments/assets/a94d6219-d804-4416-92a0-8be3156d27a7)


## Running this project

1. Add steps for running this project.
2. Make sure to include any required libraries that need to be installed for your project to run.

1. Ensure that both the Jetson Inference library and Python3 are installed on your Jetson Nano.
2. After that, download model_best.pth.tar
3. Download the dataset (images) here: (https://drive.google.com/file/d/1ZEcS-4nsMC7i7aqNkHZ_60X0bd9D3qAz/view?usp=sharing)
4. Go to the terminal and move to the classification directory:
   $ cd jetson-inference/python/training/classification
5. Set the net and data variables as shown below:
   $ NET=models/diseased_leaf
   $ DATASET=data/diseased_leaf
6. Type command to process an image:
   $ imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/blight/Late_Blight_1.jpg blight1.jpg
7. Instead, if you want to use your own unhealthy/blight or healthy leaf image, place it in one of the subdirectories within the test directory. Then, use the command above, modifying "blight/Late_Blight_1.jpg" to match the folder and filename of your image.
8. Lastly, check the output image to see if the classification is "blight" or "healthy."
View a video explanation here: VIDEO LINK YOUTUBE



[View a video explanation here](video link)
