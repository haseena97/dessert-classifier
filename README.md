# Malaysian Dessert Classifier - Project Overview

Kuih are traditional sweet or savoury cakes in Malaysia. They usually come in bite-sized form and are either sweet or savoury.<br>
![image](https://user-images.githubusercontent.com/71859510/190304266-853bc71c-a25d-4cb9-8af2-3529352a04f1.png)<br>

I built a simple web app with dessert classifier to identify the name of Malaysian desserts. This could be useful for tourists unfamiliar with Malaysian food. They could take a picture of a dessert and the app serve them some information about the ingredients (to check for food allergens), calories and whether the dessert is sweet or savoury.


I deployed the model on [HuggingFace Spaces with Gradio](https://huggingface.co/spaces/haseena97/malaysian_dessert):

![image](https://user-images.githubusercontent.com/71859510/190296726-f9d00afe-c99c-49a6-8355-7c798032f43d.png)



I was able to get the model to predict the name of the dessert with **94% accuracy** after minimal tuning. For most of the cases this would meet the need of an end user of the app. To get these results I used transfer learning on a CNN trained on resnet34.
![fine tune](https://user-images.githubusercontent.com/71859510/190294716-0a6aeaec-eed7-4789-9c7a-dcdc0dc2942d.PNG)

## Codes and Resources Used
I used Google Colab for this project as it makes the GPU configuration far easier<br>
**Python Version:** Python 3.9<br>
**Packages:** fastai, gradio, json, pickle<br>
**Fastai Course:** https://course.fast.ai/Lessons/lesson1.html<br>
**Model Building Github:** https://github.com/PlayingNumbers/ball_image_classifier<br>
**Data Collection Tutorial:** https://www.youtube.com/watch?v=vy-R4oUZaC8<br>
**Model Deployment Article:** https://tmabraham.github.io/blog/gradio_hf_spaces_tutorial<br>

## Data
I used [FatKun Batch Download Image](https://chrome.google.com/webstore/detail/fatkun-batch-download-ima/nnjjahlikiabnchcpehcpkdeckfgnohf) chrome extension to download the data from Google Images as recommended in the tutorial.

## Model Building
The notebook `classify_kuih.ipynb` takes you through the process of creating an image classifer for various types of desserts.

## Create Gradio Interface
The notebook `deployment_kuih.ipynb` takes you through the process of making the demo web app with Gradio.

## Hosting demo on HuggingFace Space
HuggingFace Spaces are essentially git repositories (like GitHub) with an `app.py` file from which the demo is prepared. Since my model file `kuih02.pkl` is too big to be handled by git, the files for deployment are uploaded via the Spaces UI. You can see the files under "Files and versions" when you go to my Space using the link provided above.

