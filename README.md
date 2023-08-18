# Fruit Classification

 This project is a retrained model of Resnet-18, and it is trained so it can better identify 5 different fruits, which are apples, bananas, mangoes, grapes, and strawberries. The model is able to classify an image of one of these fruits into it's correct class after successful training. 
 

![Image of the machine classifying an image of an apple correctly:](https://i.imgur.com/jWq6Mv5.png)

## The Algorithm

The model is able to recognize the different fruits because of the training and validation images that are fed to it. These images were compiled into a dataset on Kaggle, and I downloaded this and copied it into jetson-inference so that the images would be available for use.

Each fruit had 1940 training images, 40 validation images, and 20 test images. The training images were what the machine used to learn, the validation images help the AI further learn by giving it never seen before images to fine tune it's recognition. Finally, the test 
images are used to see the results of the training. The model was able to learn due to the pre-written python code that had been provided in the directory. 

After the model was finalized, I saved and exported it as an ONNX file, and finally I made a python file to be able 
to output the results of the test images. 

## Running this project

Set-up and training:
1. Download or make sure u have resnet-18 downloaded on your jetson nano.
2. Download all the files in the github
3. Open the fruits-data file on your device, and then drag-and-drop it into the data folder in jetson-inference/python/training/classification/data
4. Change directories back to jetson-inference, and run the command "./docker/run.sh" to navigate into the docker container
5. In the docker, change directories into jetson-inference/python/training/classification
6. Then, to train, run the command "python3 train.py--model-dir=models/fruits data/fruits-data"
7. Train for at least 20 epochs, but the more, the better.

Export:
1. When finished training, make sure you are in jetson-inference/python/training/classification
2. Run the command: python3 onnx_export.py --model-dir=models/fruits-model.
3. In your model folder, there should be an item named resnet18.onnx. This is your retrained model.

   ![Image of successful export](https://i.imgur.com/kHib88H.png)
   

Output:
1. Now that your model is exported successfully, you can try some test images.
2. Make sure you are in your project folder (final-fruit-project)
3. Use the command "python3 fruits.py fruits-data/test/Apple/Apple12.png" to test an image of an apple.
4. You can replace the path of the test image at the end of the command to try out different fruits, too.
5. There will be an output that shows you the classification as well as confidence level. 
6. For this project, the labels are as follows:
   Class #0: Apple, 
   Class #1: Banana, 
   Class #2: Grape, 
   Class #3: Mango, 
   Class #4: Strawberry,

  ![Classes](https://i.imgur.com/ng0vUTc.png) 


   

[View a video explanation here](https://youtu.be/FDTEDqGOsCo)

