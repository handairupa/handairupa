# Hi there 👋

We are <b>handairupa</b>, your personal skincare assistant.
<br>
This repo contains all of our files and steps needed to replicate it.
<br>
<br>
## Machine Learning
We used <a href=https://www.kaggle.com/datasets/dinartas/skin90>skin90</a> from Kaggle as the dataset.
<br>
Model is created for image classification using transfer learning from InceptionV3. 
<br>
Model is trained with k-fold cross validation, reaching 84% accuracy (our set threshold). Refer to the model_training.ipynb file inside the ML folder for complete documentation.
<br>
We used Vertex AI for deployment, choosing the 4-core CPU only option from a server located in Singapore.
<br>
### Deployment process
1) In GCP, open Cloud Storage --> Options and choose "Create a bucket".
2) Name the bucket. Choose single region storage, with asia-southeast1 (Singapore) as the server location.
3) Leave the other settings as default. Create the bucket.
4) Open the bucket and upload the saved model from model_training.ipynb to the bucket.
5) Open Vertex AI --> Models and choose "Import model".
6) Choose "Import as new model", name the model, and enter descriptions. Continue.
7) On "Model Settings", choose "Import model artifacts into a new pre-built container. Pick TensorFlow as the framework, and 2.8 as the version. Leave the other settings and explainability as default. Import the model.
8) Open Vertex AI --> Endpoints and choose "Create endpoint".
9) Name the endpoint, leave the other settings as default, and continue.
10) On "Model Settings", choose the model that was previously imported. Choose traffic split to be 100. Choose n1-standard-4 as the machine type. Leave the other settings as default, and create the endpoint. 

## Mobile Development
Please refer to the <a href ="https://github.com/handairupa/handairupa-app">handairupa-app</a> for complete information.

## Cloud Computing
> **TBA**
