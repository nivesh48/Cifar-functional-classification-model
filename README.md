# Cifar-functional-classification-model
A classification model from scratch using keras functional, ImageDataGenerator and Learning rate scheduler.
List of contents:
1.	cifar_functional(1).ipynb
2.	model_cifar_fun1_weights.h5
3.	training_loss.JPG
The file cifar_functional.ipynb consists of developed model using tensorflow keras functional. In will explain in detail about the architecture of model and why I choose it.
My intuition behind architecture:
1.	As a computer vision researcher, I am always concerned about the multi scale features. We know that superficial layer extract edges and corners, as we go deeper into the network the features are more abstract for classification and regression purposes.
2.	From Scale Invariant Feature Transform(SIFT), image pyramids are used to for robustness against scaled features. This is the main intuition behind Inception networks.
The architecture:
1.	First layer consists of 3X3 (conv3_1), 5X5 (conv5_1) window convolutions and concatenated (32 channels).
2.	MaxPooling (get the most weighted feature out) is used on (max_pool1) concatenated output from conv3_1 and conv5_1.
3.	We can see that using two filters enable us extracting features scaled at different levels.
4.	32 channels->64->128->256.
5.	Flattening and Dense layer with 10 nodes, softmax.
Training:
1.	I used ImageDataGenerator module to incorporate rotation of images (Augmenting).
2.	A Learning rate scheduler is used.
Notes:
1.	At the end of training for 150 epochs, we can see that our test accuracy if ~85%.
2.	It should be noted that the model is not converged fully, The trend of validation loss is declining, It means the accuracy of model can be further increased, Unfortunatly due to time constraints and without a GPU I choose only 150 epochs.
3.	But it should be noted that accuracy can be further increased.

