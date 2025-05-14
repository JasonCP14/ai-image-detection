# ai-image-detection

## Project Motivation
<p align="justify">In recent years, advancements in deep learning have led to the development of new and better generative models for various forms of media such as language and images. They have transformed many industries and helped to improve productivity [1]. However, the development of generative models have also led to an influx of deepfakes, which are media generated using artificial intelligence tools. The rise of deepfakes have significant implications as it can be used for the spread of misinformation and fraudulent activities [2]. This project seeks to show that deep learning models can be trained and used to differentiate between real and generated images.</p>

## Dataset

<p align="justify">The model will be initially trained on an image dataset from Kaggle's 2025 Women in AI Kaggle Challenge [3]. It consists of real images obtained from Shutterstock, and generated images from DeepMedia's image generative models.</p>
<p align="justify">Later on, the model will also be trained on images generated in-house, using different generative models.</p>

- Differences in Frequency Patterns:
AI-generated images often show unusual patterns in their frequency spectrum, especially in the high-frequency areas, because they struggle to reproduce very fine details.
(https://arxiv.org/abs/1911.06465)
- Uncertainty in Model Predictions:
Machine learning models tend to be less confident when analyzing AI-generated images. This is likely because the distribution of synthetic images differs significantly from that of real images.
(https://arxiv.org/html/2412.05897v1)
- Inconsistent Textures:
Generated images may include textures that look unnatural or inconsistent, especially in scenes that require complex surface details. This happens because it’s difficult for AI to model realistic textures accurately.
(https://www.mdpi.com/2073-431X/14/1/1)
- Unnatural Lighting and Shadows:
AI models sometimes produce lighting and shadow effects that don't match the geometry or context of the image, making them look unrealistic.
(https://elearn.eb.com/real-vs-ai-images/)
- Odd or Illogical Backgrounds:
Background elements in AI-generated images may appear out of place or contain patterns that don't logically connect to the main subject, which can be a clear indicator of artificial generation.
(https://elearn.eb.com/real-vs-ai-images/)



## Summary
<p align="justify">
We began by training three classifier models: CNN, ResNet, and CBAM-ResNet, on a labeled dataset sourced from Kaggle. These models were designed to distinguish between real and AI-generated images, and the initial training was aimed at establishing a strong performance baseline using real-world data.
</p>

<p align="justify">
Next, we created our own set of generative models, including a GAN, a VAE, and a diffusion model, to produce synthetic images for testing generalization. When we evaluated the classifiers on these newly generated images, their performance dropped significantly, indicating limited generalization to unseen AI-generated content.
</p>

<p align="justify">
To address this, we implemented two approaches. The first involved domain adaptation, where only the classifier heads were retrained using the generated images. The second approach retrained the entire classifier models using a combined dataset of both Kaggle and generated images. While the domain adaptation method yielded some improvement, retraining on the mixed dataset proved to be far more effective, resulting in a significant boost in classification accuracy.
</p>

The complete report can be seen in `src/report.ipynb`.