# Deep-Learning-for-Healthcare
This project part of a course `Hackathon` from **Deep Learning for Computer Vision(DLCV)** at IISc.

`Detect and match patients from before and after operation images.`

### `Winner !!` of DLCV Hackathon 2021

# Introduction
An NGO funds cataract surgeries for the underprivileged. They fund eye hospitals on basis of free surgeries performed. Funds are released, based on the number of operations performed.

The NGO needs to ensure that the funds are released only for genuine surgeries. As proof that the surgery is actually performed, the NGO currently requests eye hospitals to send in pre-operation (pre-op) and post-operation (post-op) photographs of the patient’s face for each surgery.

The NGO then verifies the pre-op and post-op images to ensure that the surgery has actually been performed before releasing funds. They also need to verify that photographs of same patients are not being sent again and again to claim funds fraudulently.

They need a system that will help in comparing these photographs to highlight cases with a high probability of fraud. These can then be further investigated manually.

# Problem statement
`Kindly refer to the attached report(pdf) details regarding our approach`

Pre-op and post-op photographs will be provided. (See figure below) The NGO needs a system that will help compare the pre and post-operative images and identify that this is the same patient with a high level of confidence.

The post-operative pictures captured, have a part of the patients' face covered with a patch. The existing facial recognition algorithms available require all the parts of the face to be visible. Hence when a part of the face is covered with the patch, these algorithms are not very effective.

The problem is to find a solution that will be able to detect and match the patients from pre-op and post-op images to confirm it is the same patient (even when a part of the face is covered with a patch)


# Brief Approach
- Created class specific image-pairs for training {1: True pair , 0: Fake Pair}
- Followed a 2-channel approach to feed in post_operation.png and pre_operation.png through a pretrained resnet18 model.
- Weights were frozen during training. Only the last Feed Forward layer was finetuned.
- Build 5 different models with roughly the same underlying principles. Final Submission was a weighted ensemble of all 5 models.

**Macro F-1 score** of our final ensemble :  `0.69462`


![alt text](https://github.com/namanjaswani27/Deep-Learning-for-Healthcare/blob/main/sample_images.png?raw=true)




