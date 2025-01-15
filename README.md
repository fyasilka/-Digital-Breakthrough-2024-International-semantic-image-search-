## Task
In this competition participants need to develop a prototype or a ready-to-implement solution capable of finding semantic copies of images that depict a similar scene regardless of the background and type of image (drawing or photo). 
## Solution 
In my solution I use pre-trained ResNet18 model, KMeans algorithm and cosine similarity between features.

The main part of the program sequentially calls functions to load and transform images, extract features, perform clustering, and find similar images. Finally, the results are visualized.

Descriotion of functions:
### load_and_transform_local_images 
This function loads images from the specified folder, converts them to RGB format (if they are black and white), resizes them (if necessary), and returns a list of image arrays and file paths.
### extract_features_with_resnet18
This function uses a pre-trained ResNet18 model to extract features from images. It takes a list of images, processes each of them, and returns a list of features.
### create_feature_dataset
The function creates a DataFrame containing indices, file names, and image features.
### perform_clustering
This function performs clustering of image features using the KMeans algorithm. By default, it creates 50 clusters.
### find_similar_images
The function finds similar images by calculating the cosine similarity between the features of the current image and other images within the same cluster.
### visualize_results 
This function visualizes the results by displaying the original image along with the similar images found.
