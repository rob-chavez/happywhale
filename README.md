# happywhale
A computer vision project


The idea of this project is simple. If a marine biolgist takes a photo of a whale or dolphin, then is there a quick way to quickly match that whale or dolphin with a database of images of whale and dolphins? Simply put, this is a matching game.


To solve this problem I first fine-tune a YOLOv9 model. I used a free trial of the open source tool called ROBOFLOW to label over 2500 images--taking about 7hrs total. What resulted was a sufficient object detection model that could identify from an image which of the 30 whale or dolphin species it belonged to that are found in this project. Additional information about the data can be found here: https://www.kaggle.com/competitions/happy-whale-and-dolphin


After developing an object detection model, I fine-tuned a RESNET50 model with training data with the goal of not predicting the species of whale or dolphin but instead using that model to produce embeddings of images. I chose RESNET50 over my original plan of using a SIAMESE NETWORK because it was already pretrained and fast to fine-tune.


Putting it all together:

(1) I start with an image and identify it's species using the object detection model.

(2) I then embed the same image with the fine-tuned RESNET50 model

(3) Using the species information from the object detection model, I filter down to only images of that species. I then use the RESNET50 model to embed all of those images

(4) Finally, I use cosine similarity to give me the closest matches.


Anyone interseted in replicating this project to conduct your own experiments can find the data on Kaggle: https://www.kaggle.com/competitions/happy-whale-and-dolphin

1. You will need to set up a GCP account---which I did with a free $300 credit trial for 90 days. I then set up a GCP storage bucket called happywhales
2. You will then need to set up a Kaggle Account and use the environment they provide to run notebook I have listed as MovingDataFromKaggleToGCP.ipynb.  This will move the data in Kaggle to your newly created GCP bucket.
3. Now you need to set up a Google Collab Account. You can use code blocks at the beginninf of the HappyWhales.ipynb to link your GCP storage bucket to your Google Collab account
4. Once your GCP bucket is attached to your Collab, you can perform your own EDA. My EDA is attached--- you will see the notes I took from Dr. Elston when I was planning this project
5. Finally, you can look at the code I wrote in the HappyWhales.ipynb noteboook to fine-tune a YOLOv9 model and to create emebeddings of the images via a ResNet50 model.
