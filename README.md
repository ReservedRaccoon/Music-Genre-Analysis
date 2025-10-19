## Music Genre Analysis
This project develops a model to classify songs into different genres based on their musical features. The approach combines several machine learning techniques, including feature vectorization, dimensionality reduction, clustering, and classification to build a comprehensive analysis pipeline.


## Project Workflow
The project follows a multi-stage process to analyze and classify music genres:

Feature Vectorization (Bag of Words): The initial dataset contained textual descriptions of musical characteristics. The Bag of Words (BoW) technique was chosen for vectorization. In this method, each unique word in the text descriptions becomes a feature, and the frequency of each word is recorded for every song. This approach was preferred over TF-IDF because some frequently occurring keywords, like 'Guitar', are highly significant and should not be down-weighted.



Dimensionality Reduction (PCA): The BoW representation resulted in a high-dimensional feature space, which is computationally intensive. Principal Component Analysis (PCA) was applied to reduce the number of dimensions while retaining most of the data's variance. This step improves efficiency and makes the data easier to visualize. The process involves standardizing the data, computing the covariance matrix, and using its eigenvectors and eigenvalues to identify the principal components that capture the most variance.





Clustering (K-Means++): To identify natural groupings in the data, K-Means++ clustering was used. This algorithm assigns each song to a cluster based on similarities in their PCA-reduced representations, helping to discover potential genre groupings without relying on predefined labels. K-Means++ improves upon standard K-Means by using a probabilistic method for choosing initial centroids, which leads to better clustering quality and faster convergence.




Genre Distribution Analysis: After clustering, the distribution of known music genres within each cluster was analyzed to evaluate the effectiveness of the clustering step. While most clusters contained a mix of genres, this is expected, as different genres often share musical attributes (e.g., synthesizers in both 'pop' and 'hip-hop').


Genre Classification (K-Nearest Neighbors): Finally, the K-Nearest Neighbors (KNN) algorithm was used to classify new songs. The model predicts a song's genre based on the majority genre of its "k" closest neighbors within the PCA-transformed feature space. The dataset was split into training and testing sets to train and evaluate the classifier.
