# Mongo DB Atlas VectorSearch Image Retrieval System

# Description
The aim of this work is to find similar images, mostly similar jean, tshirt, tv or sofa image from our dataset. We leveraged MongoDB Atlas VectorSearch feature to create the image search similarity system to retrieve the information. The dataset images have been converted into embeddings and hosted on a MongoDB Atlas cluster. For retrieval, the querying image will be first converted into embeddings then via MongoDB Atlas VectorSearch function, retrieve the top k images, where k=5 in our case. Cosine similarity is used for distance calculation. Enbeddings are generated via Vision Transformer (ViT) pretrained model. 

# Dataset
The dataset used in this work has been downloaded from kaggle and is large of 796 images, divided into 4 classes: Jean, Tshirt, TV and Sofa.

## Dataset Collection Overview
![VectorSearch_DB_Overview](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/772b850e-7c21-4659-a551-f538660fdcf9)

# Requirements
 - Transformers
 - OS
 - Pillow
 - Requests
 - Glob
 - Matplotlib
 - Numpy
 - Dotenv
 - PyMongo

# Steps
  1. Load all images from your dataset and create their embeddings via a pretrained vision transformer model.
  2. Pair image_filename and corresponding embeddings into a dictionary and store in MongoDB Atlas database.
  3. Create search index in MongoDB Atlas (see below image) to be later used for the image retrieval.
  4. Load and create embeddings for the querying image then retrieve similar images

  ## System Pipeline
  ![VectorSearch_pipeline](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/84c2140c-0d50-4d2f-956f-cdb3e854f2a0)
  
  ## Atlas Search Configuration
  ![VectorSearch](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/8eea1aef-1dda-4540-aeff-a755a0405a27)


# Results
Below we have a set of retrieval results. Based in below tests, we can observe that the system combines both the object shape and color to retrieve the perfect match. It finds the exact match of the querying image.
## Query 1
![test_result_1](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/86620315-6ccd-4dbf-8e27-78e1cc4f80c7)

## Query 2
![test_result_2](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/5ea92a5f-38ba-411a-8845-25c82db7a615)

## Query 3
![test_result_3](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/51896ef8-bd71-4053-a059-63b2691df809)

## Query 4
![test_result_4](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/3bc25f03-d5d0-4e74-a421-a770c2e53fb3)

## Query 5
![test_result_5](https://github.com/WENDGOUNDI/VectorSearch_image_retrieval/assets/48753146/eac9fde8-004f-496d-b600-67a2e9adacdf)
