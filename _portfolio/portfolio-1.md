---
title: "Infusing Stable Diffusion (Image to Image generation)"
excerpt: "For my capstone project, we worked on generating Images to create consistent images for commics. For this I focused on developing a new approach for image to image generation, where prior images could be used to bias the Stable Diffusion process.  <br/><img src='/images/Infusion.png' width='50%'> <br/> [Colab Notebook](https://colab.research.google.com/drive/1yEt098MTipqjariyV4N6So4Hif5sEhoH#scrollTo=-xMJ6LaET6dT), 
  [PDF of report](/files/Capstone.pdf)"
collection: portfolio
---

# **Infusing Stable Diffusion**  💉
*An Image Generation approach to add baisses from prior images* \

Stable Diffusion is a recent text-to-image latent diffusion model created by the researchers and engineers from [CompVis](https://github.com/CompVis), [Stability AI](https://stability.ai/) and [LAION](https://laion.ai/). It's trained on 512x512 images from a subset of the [LAION-5B](https://laion.ai/blog/laion-5b/) database. It has become largely popularized as Huggingaface has made it readily available throughd the 🤗 Hugging Face [🧨 Diffusers library](https://github.com/huggingface/diffusers). 

There exist some prior approaches for generating images from prior images such as [Img2Img](https://colab.research.google.com/github/patil-suraj/Notebooks/blob/master/image_2_image_using_diffusers.ipynb), where the biassing image is used as the initial image and denoised with stable diffusion to match the text prompt. We propose an alternative approach to Img2Img generation where Stable diffusion is initialized normally (with noisy latents), and the biassing images are fed into the model to biass the denoising steps to generate the biassing images. We call this approach Infusion as concepts are infused into the model. 

## The Approach

Briefly, here is what occurs in the Infusion approach.

A biassing image is passed through the Stable Diffusion Pipeline. That is, it is encoded into the latnet space, and fed as input into the Denoising Unet along with the current image. Within the Unet, the features of the biassing image are extracted and added to current the features (scaled) of the image currently being generated. This causes the output of the Unet to be biassed by the image, and the denoising step becomes effected by the biassing image. This effect of the biassing image starts to appear in the result.

Multiple biassing images can be sent into unet, averaging their extracted features is expected to capture higher level concepts.

## Motivation

This approach can help better understand what is occuring in the Stable Diffusion Model. The approach adds biasses at different layers of the Unet, and by changing the weights of at the different layers, it can expose the the information that is provided at the different layers of the Unet. Experimentation with the model weights gives insight into the interaction between the different layers of the unet, including the residual layers. Lastly, this method sheds light on the nature of the denoising process as a process that (a) detects features in the current image, and (b) makes them better defined.

**(Engineering Motivation)** In Stable Diffusion & the Img2Img approach, the model (Unet specifically) uses the features that exist in the image to denoise them, and make them more realistic. That is, if there is a green circle with some noise, the Diffusion approach will remove this noise leaving only the green circle. The Infusion 💉 approach moves this process into the Unet Model itself. It adds features of the Biassing Image to the current features within the Unet Model. This has the effect of recognizing features from the biassing image itself, and denoising them into existance. That is, the process generates the biassing image rather than starting with the initial image. View the following image as an example. 

<div style="display: flex; justify-content: center; align-items: center;">
  <img src="https://drive.google.com/uc?id=10wmCABBaKBvuuRprhSm49uWB60Ae9xZo" width="300"/>
</div>

**(Psychology Motivation)** In psychology/neuroscience there is a concept of top down processing where thinking of something influences what we precieve. For example, in the following image, looking at the middle character, it transforms between the letter 'B' and the number '13' depending on whether we focus on 'ABC' or '12 13 14'. Infusion aims to act as a similar approach in that adding features (thinking of a concept) from a biassing image, causes it to appear in the generated image. 


<div style="display: flex; justify-content: center; align-items: center;">
<img src="https://practicalpie.com/wp-content/uploads/2021/11/ABC-12-13-14.jpg" width="300"/>
</div>