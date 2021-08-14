## interview-scripts
A few polished scripts for postdoc interviews. All the scripts are in Python and uploaded in Jupyter Notebooks for easy visualization. You can download the script or just open them in your browser. More info:

# AlexNet_embeddings
How can we know if a pattern of results can be reasonably explained by perceptual (dis)similarity? In other words: what categories of images are perceptually distinct from each other, and what can this tell us about the brain? I wrote this script to explore the idea that the pattern of results we saw in our fMRI decoding analysis could be replicated by a computational model mimicking the early layers of the ventral visual stream. 

This script is part of an fMRI pipeline. In this study, we shown visual stimuli belonging to 2 categories (faces, vehicles) and 4 sub-categories (cars, bikes, male and female faces) to 24 subjects. We collected, preprocessed and analysed the fMRI data, and performed a Multi Voxel Pattern Analysis on the beta images. The results from this analysis showed above chance accuracy for all the possible comparisons, except for perceptually similar categories (e.g., female vs male faces). But how do we actually know what categories are perceptually similar? One solution that I implement here is to feed our images to a computational model performing basic low-level perceptual tasks, and run a similar classification analysis on the activation of the network. Here we chose the first convolutional layer of AlexNet. If we see above chance classification accuracy between two categorie of stimuli, then we can assume that these two categories are perceptually different for the network. Answering this question can help us understanding the nature (categorical vs. perceptual) of the information we found in our fMRI data. 

This is what the script does in a nutshell: we import the images, we load the netwok and plot the weights of the first convolutiona layer. we pass all the images through the network, and we extract the activation from the first convolutional layer for each image. We apply different levels of noise to the dataset, reduce the dimensionality and perform a classification analysis. Finally, we plot the results.
