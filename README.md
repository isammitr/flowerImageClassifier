# Deep Learning Project: To create an  Image Classifier
Implemented a convolutional neural network to classify images from the CIFAR-10 dataset. (To classify flower images into 102 different species).</br>
Each step has been discussed in the `Image Classifier Project.ipynb` jupyter notebook. </br>

- Loading the data
  - After the data was loaded, transformations were applied, to the training data, such as scaling, cropping, and flipping to 
    help the neural network generalize leading to better performance.
  - No transformations were applied to the validation and testing dataset but these were resized and cropped so that all the
    images would be equal in size.
  - Further all the images were converted into tensors and then normalized as per their means and standard deviations.
  - Performed dictionary mapping of the integer encoded categories to the actual names of the flowers.
  
- Building and Training the Classifier
  - Loaded a pre-trained network (densenet121)
    - input nodes: 1024
    - hidden units: 512
    - output nodes: 102 (one for each category)
  - Defined a new, untrained feed-forward network as a classifier, using ReLU activations and dropout
  - Trained the classifier layers using backpropagation using the pre-trained network to get the features
  - Tracked the loss and accuracy on the validation set to determine the best hyperparameters
  - Saved the model as a checkpoint (`checkpoint.pth`) so that it can be reused later.

- Inference for classification
  - Wrote a function called predict that takes an image and a model, then returns the top $K$ most likely classes along with
    the probabilities.
