# AlexNet-Feature-selection-with-SI

In a convolutional neural network, by passing the input data through the filters, we reach a new space where some of the obtained features may not have useful information to separate the classes from each other in the classification process. In this case, you can use the methods that exist to reduce the dimension and select the effective features. In this project, the aim is to use the SI complexity index for feature selection and dimensionality reduction in the AlexNet model.

!! It should be noted that the purpose of this project is to show the effect of reducing features and reducing dimensions using the Separation index method !!

In AlexNet_model.ipynb, we build the AlexNET model by adding pooling layers after each convolution layer (to reduce the number of features) and train the model with 1220 data from the MNIST dataset (which is separated from the original MNIST dataset in a balanced way) and save the model.
The final accuracy of the network (AlexNet model with the addition of pooling layers, training and evaluation with the mentioned small dataset) on the test data: 96.78%

In "Dimension reduction using SI.ipynb" section "Part1" we have given the mentioned data set as input to the pre-trained network in "AlexNet model.ipynb" and then we have started Selection Forward, like this We select the features of the last layer of the network before the classification layer in order until the "SI" value reaches the maximum value and the SI value does not change significantly with the increase in the number of features.(For this, we use Kalhor_SeparationIndex)

![image](https://github.com/user-attachments/assets/2aed5fa2-f95e-4e38-9398-c96b4ad9b0a1)

As it is clear from the above diagram, "SI" occurs in the maximum number of 288 features. (Although we can easily say that there is no noticeable change in the "SI" value after 40 features, but to increase the accuracy, we choose the point where the maximum SI occurs.)
So we can consider the effective features of the network as its first 288 features

In the "PART2" section, we remove the classifier layers from the current model (the trained ALEXNET model) and this time we apply the classifier to the features obtained in the "PART1" section and train the classifier and And finally we evaluate this new model.(training and evaluation with the mentioned small dataset)

The final accuracy of the new model on the test data: 96.14%


In "Each_Layer_SI.ipynb", the values ​​of "SI" in each layer are calculated in the trained "AlexNet" model saved in "AlexNet_model.ipynb".
The work process is that in each layer of this network, using the mentioned dataset, "SI" is calculated and the graph of the change of "SI" in each layer is finally drawn.
The final plot for the training dataset is below.

![image](https://github.com/user-attachments/assets/33e2c667-410e-4702-a363-bd59a50fa5fb)

As expected in the above plot, the value of "SI" is generally increased by moving forward in the layers, which means that by moving forward in the layers, the output features become more distinguishable. This work shows well the progress and work of the layers of a network.





