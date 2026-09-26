# Transfer Learning Based Butterfly Image Classification

## Aim

To implement transfer learning using pretrained **AlexNet, VGG16, ResNet50, and EfficientNetB0** models for butterfly image classification and compare their performance.

## Dataset

The project uses a Butterfly image dataset containing images of different butterfly species.

For this experiment, five butterfly classes are selected. A maximum of 100 images are used from each class to keep the dataset small and suitable for training.

The selected dataset is divided into:

* **70% training data**
* **30% testing data**

## Technologies Used

* Python
* PyTorch
* Torchvision
* Pandas
* Scikit learn
* Matplotlib
* Pillow

## Methodology

The images are first resized to **224 × 224 pixels** and converted into tensors. ImageNet normalization is applied because the selected models are pretrained on ImageNet.

Four pretrained convolutional neural network models are used:

* AlexNet
* VGG16
* ResNet50
* EfficientNetB0

The original classification layer of each model is replaced with a new classification layer containing five output classes.

The pretrained feature extraction layers are frozen, while the new classification layer is trained using the butterfly dataset.

## Transfer Learning

Transfer learning allows a model trained on a large dataset such as ImageNet to be reused for a new image classification task.

In this project, the pretrained models provide general image features such as edges, textures, shapes, and patterns. The final classification layer is adapted to classify the selected butterfly species.

## Training

Each model is trained using:

* **Optimizer:** Adam
* **Loss function:** Cross Entropy Loss
* **Batch size:** 16
* **Epochs:** 3
* **Input image size:** 224 × 224
* **Pretrained weights:** ImageNet

Only the newly added classification layer is trained, while the pretrained layers remain frozen.

## Evaluation

After training, each model is evaluated using the testing dataset.

The main evaluation metric is **test accuracy**.

The accuracy of all four models is stored and displayed for comparison. A bar graph is also generated to visualize the performance differences between the models.

## Workflow

```text
Butterfly Dataset
        |
Select Five Classes
        |
Limit Images Per Class
        |
Train Test Split
        |
Image Resizing
        |
Image Normalization
        |
Load ImageNet Pretrained Models
        |
Replace Classification Layer
        |
Freeze Pretrained Layers
        |
Train Classification Layer
        |
Evaluate on Test Data
        |
Compare Model Accuracy
```

## Models Compared

| Model          | Main Characteristic                                       |
| -------------- | --------------------------------------------------------- |
| AlexNet        | Early deep CNN architecture using convolutional layers    |
| VGG16          | Deep CNN using repeated small convolution filters         |
| ResNet50       | Uses residual connections to support deeper networks      |
| EfficientNetB0 | Uses a compound scaling approach for efficient CNN design |

## Expected Output

The program produces:

1. Sample butterfly images
2. Training accuracy and loss for each model
3. Test accuracy for each model
4. Final accuracy comparison
5. Bar graph comparing model performance

The actual accuracy values depend on the selected images, training process, hardware, and model initialization. Therefore, the values generated during execution should be used in the final result table.

## Conclusion

The experiment demonstrates how transfer learning can be used for butterfly image classification using pretrained CNN models. The performance of AlexNet, VGG16, ResNet50, and EfficientNetB0 is compared using their test accuracy on the same dataset and evaluation procedure.
