# Anime-Video-Generator
Pose guided Anime Video Generator using Deep Learning. Its a self project created being inspired by StyleGAN2, PSGAN and Unsupervised Image-to-Image translation.

## Idea and Goal

Well in the current revolutionising digital world, animated videos are making a huge impact over society. Every person irrespective of their age group loves to watch animated videos because its engaging not only in terms of entertainment but also educative. As its getting day by day popular among millenials or middle class person, still there's a part of society who cannot afford such electronic gadets or have cable connection or subscriptions of TV channels, running such animated programs. So, this project Idea arise from this thought, to why not use Deep learning (especially, Generative Adversarial Networks) to design such model which can generate Animated Videos directly from Real time videos recoreded from Mobile and this available to every class of society. 

### Approach
The Idea behind this project is to generate Anime video (Target Video) from corresponding real time human video (Source Video). 
The Idea is split into three parts - 

    1. Split video into Frames
    2. Extract the pose sequence for each person from each frame.
    3. Generate the Anime character corresponding to each pose sequence.
 

## Pose Estimation

This part deals with the Human pose estimation. Human Pose Estimation is defined as the problem of localization of human joints in images or videos. This represents the orientation of the person in that frame. So, graphically, human pose represents the coordinates of joints ( Elbow, knee, wrist, etc) based on person orientation.

It can be of two types -

    2D Pose Estimation - Estimate a 2D pose (x,y) coordinates for each joint from a RGB image.
    3D Pose Estimation - Estimate a 3D pose (x,y,z) coordinates from a RGB image.

Human pose estimation is a heated topic now day as it has a wide application like gaming, security survelliance, animation etc. There are several approaches for pose estimation using Deep learning like OpenPOSE, DensePOSE and MaskRCNN, etc. As this project deals with the multiperosn in the video, more accurate the object detection model will be, higly efficient the pose estimation is. So, the idea is to use pretrained model of DensePose or OpenPose to extract the keyjoints for this task, as they have shown remarkable results till now compared to other Pose estimation approaches.       


## High resolution Anime Image synthesis from Pose Sequence

Once we have the pose, the next step is to translate those pose into a Anime character. This can be acheived in both the ways i.e. Supervised and Unsupervised. 
For supervised way, we have to prepare custom dataset of Paired images ((Pose) <-> (target Animes)) and train Deep Learning models like Pix2Pix GAN, a very popular GAN architecture for Image to Image (I2I) translation. Other variant of Pix2Pix is Pix2PixHD, that is capable of generating High Resolution and fine grained images. 

But for this project, best way will to use Unsupervised way, as custom dataset creation is not feaible solution. The reason behind this is that the generated anime character should preserve the sementic charactersitcs of the Input Image (i.e. it should resemble similar to the person in the video frames). Now the point is that input video can contain N number of unknown person, so to create custom dataset corresponding to them is a difficult task. So for this task unsupervised learning is the better approach for Pose to Anime generation. Several research work has been published focusing on Unsupervised way of Image synthesis from a latent noise. Out of various State of the Art generative appraches Progressive Generative Adversarial Network, StyleGAN and its variant StyleGAN2 has proved to be a good choices for High resolution image synthesis. 


## Related Work

### Image to Image translation


### Video to Video translation

## References
