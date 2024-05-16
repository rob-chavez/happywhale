# happywhale
A computer vision project

The notebooks in this repo were used to complete a project for CSCI-25 (Computer Vision). Anyone interseted in replicating this project to conduct your own experiments can find the data on Kaggle: https://www.kaggle.com/competitions/happy-whale-and-dolphin

1. You will need to set up a GCP account---which I did with a free $300 credit trial for 90 days. I then set up a GCP storage bucket called happywhales
2. You will then need to set up a Kaggle Account and use the environment they provide to run notebook I have listed as MovingDataFromKaggleToGCP.ipynb.  This will move the data in Kaggle to your newly created GCP bucket.
3. Now you need to set up a Google Collab Account. You can use code blocks at the beginninf of the HappyWhales.ipynb to link your GCP storage bucket to your Google Collab account
4. Once your GCP bucket is attached to your Collab, you can perform your own EDA. My EDA is attached--- you will see the notes I took from Dr. Elston when I was planning this project
5. Finally, you can look at the code I wrote in the HappyWhales.ipynb noteboook to fine-tune a YOLOv9 model and to create emebeddings of the images via a ResNet50 model.

