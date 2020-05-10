# Traffic_Sign_Classifier-with-Streamlit

## Project overview
- The aim of this project is to focus on the first fundamental features of the decision making ability of an autonomous vehicle, 
i.e., to develop a deep learning model that reads traffic signs and classifies them correctly using Convolutional Neural Networks(CNNs).

- The traffic sign classifier uses a German traffic dataset. The German traffic dataset consists of
34,799 32*32 pixels colored images that is used for the training dataset, 12,630 images are used
for the testing dataset and 4410 images are used in the validation dataset where each images is a
photo of a traffic sign belonging to one of the 43 classes i.e., traffic sign types.

## Dataset:
Train Data: https://drive.google.com/open?id=1ZrJJvIbZ5vUHjyzUGNXGl4sRS7zlU5Db

Validation Data: https://drive.google.com/open?id=1bLWaYJZHroOyfPVscVdBjh9atjvHDdFj

Test Data: https://drive.google.com/open?id=127Usik6jjD_oBhr5hDojgLARW9XYxWdr

## Folders Description
### Google Colab Notebook
#### Contains the whole process of building the CNN Model 
- Load the Pickled dataset
- Use Seaborn to visualise the data.
- Preprocess the images using OpenCV.
- Use ImageDataGenerator for image augmentation and help the model generalise it's results.
- In our build_model(hp) function we start building our CNN model using KerasTuner and then compile our model.
- KerasTuner gives us the best hyperparameter combinations using RandomSearch method.
- We now create a model checkpoint and then fit the model and run it for 40 epochs.
- Now Load the model's weights and biases and evaluate it on our test dataset.
- Save our model in Keras HDF5 format.
- Use the saved model to test on random images.

### Streamlit App

### Model
Contains the saved keras model named
- ###### Traffic_sign_classifier_CNN.hdf5

### App
classify.py
- get_model(): Loads the saved model into cache using streamlit's "@st.cache" feature.
- predict(): Takes an image as input from the function parameter, preprocesses it and feeds it to the model for results.

upload.py
- Contains the front-end code for the streamlit app.
- Imports the predict() function fetches the result and displays it.

### Test Random Images
- This contains images from the internet. A total of 43 images belonging to each class.
- Our model will be tested using this unseen data
