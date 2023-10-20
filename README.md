# Classifying Flower Images using Convolutional Neural Networks

Waiting for the evaluation results on the Private Dataset

## Dataset
The provided dataset contains 70 images of 5 types of flowers, making it in total 350 images.
It could be considered as a small dataset in terms of number of images, therefore some steps
have been made to ensure that the model will be robust. First of all, 5 samples from each of
the classes have been randomly selected and moved to a “test” folder for later evaluations.
Next, the number of images in the “train” set has been doubled by adding the original with
the augmented versions into the mix. The image augmentations that have been used are:
- Rescaling to a range between 0 and 1.
- Randomly Rotating in a range of 40 degrees.
- Randomly Shifting.
- Randomly Scaling.
- Randomly Horizontally Flipping.
- Resizing to (224, 224).

With that, the project had 650 images during the training phase where 10% of it was
dedicated to the validation process. The split was done using the train_test_split method from
sklearn with shuffle=True and using stratify.
The labels arrays have been encoded for the model using the TensorFlow’s to_categorical
method, e.g. [0,1,0,0,0].

## Model

I have implemented one of the most popular CNN architectures, AlexNet.
AlexNet was developed by Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton. It won the
ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2012 and was tested numerous
times. Using the official documentation [1] and layers from the Tensorflow, it was made from scratch
without any pre-trained weights.

![Model implementation](https://github.com/DexMerc/Flower-Classification-Simple/blob/master/imgs/model.png)


For the training process, ‘Adam’ for optimizer and ‘categorical_crossentropy’ for loss were chosen,
the epoch was set 50 and batch size was 32.

## Results

At the last epoch, the model achieved 99.66% accuracy during the training and 84.62% accuracy
during the validation.

![Accuracy and loss graph](https://github.com/DexMerc/Flower-Classification-Simple/blob/master/imgs/acc_loss.png)

After testing it on our small “test” dataset, the model predicted flower images with 100% accuracy.

![Accuracy and loss graph](https://github.com/DexMerc/Flower-Classification-Simple/blob/master/imgs/test.png)



## References
1. Krizhevsky, A., Sutskever, I., & Hinton, G. E. (2012). Imagenet classification with deep
convolutional neural networks. Advances in neural information processing systems, 25.
