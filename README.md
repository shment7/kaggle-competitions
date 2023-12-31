# Facial Keypoints Detection
https://www.kaggle.com/competitions/facial-keypoints-detection


Landmark detection problem.

We want to detect facial keypoints (nose, eyes, etc) location in a face image.

Data consists of 7,049 images.

Some of the images have 15 keypoints and some have only 4 keypoints.

1. Use EfficientNet V2, DenseNet201, MobileNet V3 and InceptionNext with pretrained weights that were trained on ImageNet with additional hidden layer at the end to reduce output dimension to 30. All weights are learnable.
2. batch size=64, learning rate=0.001, number of epochs=210, mse loss.
3. AdamW optimizer with weight decay=0.1 and learning rate decay by a factor of 0.25 every 30 epochs.
4. Augmentations - rotate image by up to 20 degrees clockwise or counter clockwise, black 5% of pixels, gaussian blur.
5. Since some of the images have only 4 keypoints and network output 30 numbers, loss for images with 4 keypoints is computed by ignoring rest of the network output.
6. Prediction is the mean of the above 4 models.

   
Results:

Public leaderboard - 1.52189 rmse - 1st place.
Private leaderboard - 1.24299 rmse - 1st place.
