
# mandiLens
[![License](https://img.shields.io/github/languages/top/bhuvannarula/mandiLens)](https://img.shields.io/github/languages/top/bhuvannarula/mandiLens)
[![training](https://img.shields.io/badge/validation%20accuracy-94.38%25-brightgreen)](https://img.shields.io/badge/test%20accuracy-97.04%25-brightgreen)
[![training](https://img.shields.io/badge/test%20accuracy-97.04%25-brightgreen)](https://img.shields.io/badge/test%20accuracy-97.04%25-brightgreen)

*scan&find* which building you're looking at.
**Exclusively for IIT Mandi.**

## Installation

Just open  the Google Colab .ipynb file in Google Colaboratory.

#### For custom-training, (ignore for just prediction)

To access dataset, you need to mount your Google Drive,

[Google Drive Link to Dataset](https://drive.google.com/drive/folders/1zgTsQeSgFrRdetevS7V3vbUyVmDlq17x?usp=share_link)

Create a shortcut of the drive above in your drive, such that the path becomes, ('dataset' is the data folder)
```
[Your Google Drive]/dataset/...
```
    
## Documentation

The Jupyter Notebook includes detailed explaination of code, along with how to use it to train the model.

User can upload an image, and predict for the same using Google Colab Notebook.
## Problem Statement
We were needed to create a Convolutional Neural Network, which can predict the building to which the Image provided belongs to.

We have created dataset ourselves, which includes different buildings in North Campus, IIT Mandi, and the classes are namely,
- A9
- A10
- A13
- A16 (Central Library)
- A17
- OAK (Oak Mess)
- TRAGOPAN (Tragopan Canteen)
- flower1 (Marigold Flower)

We were also required to provide a way for user to upload their own image, upon which we then predicted the class it belongs to.
## Working & Implementation

We have implemented our CNN Model in a Google Colab Notebook. We have trained the model ourselves, and saved the same in GitHub, which the user can directly use for prediction.

The implementation uses a pre-built **VGG19** Model, which is a 19-layered Deep Convolutional Neural Network. For weights, we have used the pre-trained weights on 'imagenet' dataset.

We have removed the top of model, and included two custom layers,
- Flatten
- Dense(8) (since we have 8 classes)
These layers act as the output layers, and we trained the parameters for these layers.

We chose *'adam'* as our optimizer, and *'categorical_crossentropy'* as our loss function, and *'accuracy'* as our metrics during compiling of model.
## Metrics of Model
Parameters used,
- Batch-Size = 16
- Epochs = 10
We were able to achieve following accuracies,
- Validation Accuracy : **94.38%**
- Testing Accuracy : **97.06%**
The *model* corresponding to these metrics has been saved as 'savedModels/model.h5' in this GitHub Repository. Same can be imported in the Google Colab Notebook and be used for prediction and accuracy metrics. Provision for same is implemented in the notebook.
## Roadmap

- Improve and increase the dataset to include more buildings & around IIT Mandi

- Create a custom-implemented YOLO model, which can predict the buildings in bounding boxes, using the live-feed of a camera.

- Develop an Android-App which can implement YOLO model on live camera feed.

