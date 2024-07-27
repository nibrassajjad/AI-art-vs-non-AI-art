# AI art vs non AI art
An algorithm to classify AI-generated images from human-created images.

# Training and deployment code
Proceed to Models folder for further details regarding code. The original code has been executed on Kaggle notebook:

<br>Training model code:
<br>https://www.kaggle.com/code/nibrastuhh/ai-artbench-ai-vs-human-art-detection-90-acc
<br>Deployment classifier code:
<br>https://www.kaggle.com/code/nibrastuhh/ai-artbench-classifier-tool-v2

# Project Objective
The goal of this project is to create a Convolutional Neural Network (CNN) classifier that distinguishes between AI-generated and human-created art using supervised learning techniques.

# Dataset
**AI-ArtBench** dataset has been used which contains over 180,000 art images. The dataset is made up of arts in the following style (both AI and non-AI): Nouveau, Baroque, Expressionism, Impressionism, Post-Impressionism, Realism, Renaissance, Romanticism, Surrealism and Ukiyo. 60,000 of them are human-drawn art that was directly taken from ArtBench-10 dataset and the rest is generated equally using Latent Diffusion and Standard Diffusion models.

Link to dataset: https://www.kaggle.com/datasets/ravidussilva/real-ai-art

![image](https://github.com/user-attachments/assets/c31ad34c-1da3-4e05-a678-ea867e57604d)

# Reshaping input
The CNN algorithm takes input in the form of pixels. The higher the pixels, the more complex the model is going to be with higher training time. This is why input is downscaled before being fed to the algorithm.

Two models has been created for experimenting:
<br>**[Model 1:](https://github.com/nibrassajjad/AI-art-vs-non-AI-art/tree/main/Models/AI-artbench/model%201%2032px)** Reshapes input image at 32 x 32 pixels
<br>**[Model 2:](https://github.com/nibrassajjad/AI-art-vs-non-AI-art/tree/main/Models/AI-artbench/model%202%20128px)** Reshapes input image at 128 x 128 pixels
![image](https://github.com/user-attachments/assets/fa0ff6af-2269-45b0-a951-54720c7a9aef)

# CNN architecture
A CNN architecture following [Bird & Lofti’s paper](https://arxiv.org/pdf/2303.14126.pdf) has been used. An accuracy of over 90% was achieved from this.

<img src="https://github.com/user-attachments/assets/2b7aca56-3e59-4cfd-8415-70c5aef895f8" style="width:600px;" />

# Training and Testing set
Training set: 50000 human-drawn and 50000 AI-generated arts
<br>Testing set: 10000 human-drawn and 20000 AI-generated arts (10000 Latent Diffusion and 10000 Standard Diffusion models)

# Result matrices
![image](https://github.com/user-attachments/assets/74f1bdc1-6b10-4add-87c9-9ba7d6499f42)

# Result summary
* Both models produced 90%+ F1-score for classifying AI and non-AI arts.
* Models perform comparatively better in detecting AI-arts.
* Despite Model 2 having 4 times the input pixel size, both models show minimal deviation in accuracy.
* However, how both models classifies an image can be different nonetheless as can be seen when the classifier models were applied on the hand-picked augmented images in [this directory](https://github.com/nibrassajjad/AI-art-vs-non-AI-art/tree/main/Datasets/new%20sample).
* Summary of classification scores for these images:

![image](https://github.com/user-attachments/assets/dfa3e939-76ab-436f-88d0-3062ed07fb66)

# Explainable AI (XAI) qualitative analysis approach for understanding classification mechanics
XAI helps make AI decision-making processes understandable to humans. Visual analysis based on results from hand-picked augmented images aids in decision-making about which model classifier to use based on specific situations.

# Interpretations made based on classification score on the hand-picked augmented images

<img src="https://github.com/user-attachments/assets/9a65769a-f1c8-48bb-832e-c119df946498" style="width:800px;" />


# Comparison between models

<img src="https://github.com/user-attachments/assets/222cf456-b804-48ed-864e-32b3d5ba5b33" style="width:700px;" />

# Purpose of qualitative analysis

* The ultimate objective is to investigate how variations in image augmentations affect the algorithm's sensitivity to distinguishing between human-drawn and AI-generated artworks.
* Identify potential vulnerabilities or weaknesses in the algorithm's performance when faced with specific types of image alterations.
* Emphasis on how insights gain from research like this can emphasize our understanding of the algorithm better and we can make improvements based on such studies.

# Author notes

If you liked this project, please leave a star! I am currently looking for job opportunities, preferably in Germany. Feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/nibras-sajjad/) if you have any leads or would like to connect.

























