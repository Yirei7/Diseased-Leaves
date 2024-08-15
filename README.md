# Project Name

 This project allows the user to identify how much a leaf is diseased. It is be useful for avoiding inedible leaf vegetables.

![image](https://github.com/user-attachments/assets/479e4d28-492d-48f6-b1db-ea7ea09b9222)

## The Algorithm

This project was created using the Jetson Nano. The model is essentially a retrained resnet-18, trained on a dataset containing various leaves, each labeled with their corresponding class (either blight or healthy). When the model is executed, it uses the imagenet.py program along with the trained model to classify the leaf's health from a given image.

![image](https://github.com/user-attachments/assets/a94d6219-d804-4416-92a0-8be3156d27a7)


## Running this project

1. Ensure that both the Jetson Inference library and Python3 are installed on your Jetson Nano.
2. After that, download model_best.pth.tar and resnet18.onnx: (https://drive.google.com/file/d/1t8FY9F9BrWKe0JKP6-7QUr6bEoDbvZpB/view?usp=sharing) (https://drive.google.com/file/d/13xnW1Gkq7pUpCK92jZrR4AZBrP3QK1QQ/view?usp=sharing)
4. Download the dataset (images) here: (https://drive.google.com/file/d/1ZEcS-4nsMC7i7aqNkHZ_60X0bd9D3qAz/view?usp=sharing)
5. Go to the terminal and move to the classification directory:
   '''$ cd jetson-inference/python/training/classification'''
6. Set the net and data variables as shown below:
   $ NET=models/diseased_leaf
   $ DATASET=data/diseased_leaf
7. Type command to process an image:
   $ imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/blight/Late_Blight_1.jpg blight1.jpg
8. Instead, if you want to use your own unhealthy/blight or healthy leaf image, place it in one of the subdirectories within the test directory. Then, use the command above, modifying "blight/Late_Blight_1.jpg" to match the folder and filename of your image.
9. Lastly, check the output image to see if the classification is "blight" or "healthy."
View a video explanation here: https://youtu.be/tkCVzYpyIuY
