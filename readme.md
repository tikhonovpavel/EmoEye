# **EmoEye team Final Project page for Deep Learning course**
This repository contains the code for the final project course on deep learning, which aims to build a multimodal architecture for emotion prediction problem. The goal of this project is to build and fine-tune multimodal neural network for prediction of Emotions based on Eye-Tracking and biometric data. The dataset itself is private, but preprocessed data will be available for some time [here](xxx).

# **Dataset**
We used private dataset containing 29,153 5-second reactions from 160 participants to 799 Images. Images are very diverse and contain scenes, people, animals, etc.
After 5 seconds of Image presentation, participants reported the percieved emotion on Arousal (from 1 to 7, from boring to exciting) and Valence (from 1 to 7, from negative to positive) scales.
During 5 seconds of Image presentation the following data were collected:
1. The eye-tracking data - X, Y coordinates on the picture at which participant was looking at
2. The pupillometry data - sizes of the pupils
3. Galvanic Skin Response (GSR)
4. Heart Rate (HR)
Note, classes of target variables - arousal (1-7) and valence (1-7) - are highly imbalanced and correlated.

## **Project presentation**
#### [Final project presentation](xxx)

# **General Project Goals**
X and Y coordinates of eye-tracking data may be naturally represented as an image of scanpath (Fig. 1) that may be analyzed via Convolutional Neural Network (CNN). At the same time we still have some additional time-series biometric data (pupil size, GSR, HR) that may be analyzed via Recurrent Neural Network (RNN). So, a natual idea is to implement CNN and RNN at once in multimodal neural network by concatenatination of CNN and RNN outputs (this approach is described in [this](https://dl.acm.org/doi/10.1145/3382507.3418828) article[^1]). We implemented this approach on our private dataset and improved it by adding extra module processing the Image shown to the participant.
[^1]: Sims, S. D., & Conati, C. (2020). A Neural Architecture for Detecting User Confusion in Eye-tracking Data. 
Proceedings of the 2020 International Conference on Multimodal Interaction. doi:10.1145/3382507.3418828.

# **Implemented tricks for training procedure**
1. Focal loss (gamma=3) - we saw this problem as classification problem not regression, and focal loss greatly improved performance. We also set balanced class weights into CrossEntropyLoss.
2. Dataset balancibg - it's close to impossible to balance dataset for both arousal and valence classes, we aplied some heuristics to create subset of data with close uniform class distribution.

# **Methods**
Resulting multimodal network consists of three parts:
1. CNN-LSTM to analyze time seies data (X, Y, pupil size, GSR, HR)
2. CNN to analyze scanpaths
3. VGG16 to analyze Images (visual stimuli)

During training, only top layers of VGG16 were unfrozen.

# **Repository structure**
1. Notebook "Multimodal_network" - notebook with dataloaders, train-test loops and implemented in pytorch multimodal network
2. Notebook "Separated_networks" - notebook with dataloaders, train-test loops and implemented in pytorch parts of multimodal network
3. Notebook "Augmentation" - notebook to augment Images and Eye-tracking data at once. We didn't have time to train with augmentations, but it works!

# **How to Use**
1. Download data [here]()
2. Unzip data at the same folder where notebooks are located
3. Run notebooks. Each notebook may be treated separately.

# **Conclusions**
(some accuracy percentages and tables)

# **Prerequisites**
...

# **EmoEye Team**
...

# **Thanks!**
<img src="Docs/Мем(очень смешной(нет)).jpg" alt="Meme" width="800">
