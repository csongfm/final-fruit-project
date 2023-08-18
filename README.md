
# Fruit Classification

 This project is a retrained model of Resnet-18, and it is trained so it can better identify 5 different fruits, which are apples, bananas, mangoes, grapes, and strawberries. The model is able to classify an image of one of these fruits into it's correct class after successful training. 
 

![add image descrition here](direct image link here)

## The Algorithm

The model is able to recognize the differen fruits because of the training and validation images that are fed to it. These images were compiled into a dataset on Kaggle, and I downloaded this and copied it into jetson-inference so that the images would be available for use.
Each fruit had 1940 training images, 40 validation images, and 20 test images. The training images were what the machine used to learn, the validation images help the AI further learn by giving it never seen before images to fine tune it's recognition. Finally, the test 
images are used to see the results of the training. The model was able to learn due to the pre-written python code that had been provided in the directory. After the model was finalized, I saved and exported it as an ONNX file, and finally I made a python file to be able 
to output the results of the test images. 

## Running this project

1. Add steps for running this project.
2. Make sure to include any required libraries that need to be installed for your project to run.

[View a video explanation here](video link)
[readme.md](https://github.com/csongfm/Fruit-recognition/files/12383340/readme.md)
