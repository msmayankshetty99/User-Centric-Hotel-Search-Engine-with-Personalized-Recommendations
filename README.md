# User-Centric-Hotel-Search-Engine-with-Personalized-Recommendations
Project Overview
This repository contains the implementation of a hotel search engine that leverages user preferences to suggest hotels aligned with their tastes and amenity requirements. The search engine uses data from hotel reviews to provide personalized recommendations, making it easier for users to find accommodations that best suit their needs.

Goals
In the digital age, personalized content selection is essential due to the vast amount of information available online. This project aims to develop a hotel search engine that suggests hotels based on user preferences derived from hotel reviews, rather than just searching for hotel names and locations. The system analyzes user reviews using text retrieval and machine learning models to provide tailored recommendations.

Dataset
The dataset used for this project is the "515K Hotel Reviews Data in Europe," which can be found on Kaggle here. It contains:

515,000 reviews of 1493 hotels across Europe
Hotel name, address, average score, number of reviews
Review date, reviewer score, positive and negative reviews
Word counts for positive and negative reviews
Feature tags (e.g., amenities, customer services)
Reviewer nationalities, number of reviews given by each reviewer
The data is collected from Booking.com and is labeled with a public domain license.

Methodology
The search engine implementation includes four different approaches using Word2Vec models and similarity metrics:

Custom Word2Vec + BM-25 with doc length normalization
Custom Word2Vec + Word2Vec log-likelihood (one vector per word)
Pre-trained Word2Vec + Word2Vec log-likelihood (one vector per word)
Pre-trained Word2Vec + Word2Vec log-likelihood (one representative vector per review)
Pipeline Design
Preprocessing: Clean and preprocess the dataset by removing trivial information, stemming, removing numbers and punctuation, making text lowercase, and removing extra spaces.
Tag Association: Associate tags with positive reviews and train the custom Word2Vec model using positive and negative reviews.
Word Combination: Combine words with similar meanings within each review using the custom Word2Vec model.
Query Processing: Preprocess the query and obtain its embeddings using the Word2Vec model.
Similarity Computation: Compute similarity scores between the query and reviews, combining positive and negative review scores.
Location Filtering: Convert the user-provided location into coordinates using Geocoding API and filter hotels based on location.
Output: Output the filtered hotels ranked by the computed score.
Evaluation
The system's rankings are compared with Booking.com's rankings for the same query and location. Sample queries about amenities (e.g., "hotel with swimming pool and car parking") are used to verify the system's accuracy. The top-ranked hotels returned by the search engine were found to have the specified amenities, indicating the system's effectiveness.

Discussion
The project demonstrates the potential of developing a real-time, personalized hotel search engine. Future work could explore:

Utilizing the entire dataset for potentially more accurate results.
Investigating the tradeoffs between using pre-trained and custom Word2Vec models.
Enhancing the system with larger datasets and more diverse queries.
Contributors
Rachanon Petchoo - petchoo2@illinois.edu
Mayank Shetty - mshetty4@illinois.edu
Viraj Shah - virajns2@illinois.edu
Pallaw Kumar - pallawk2@illinois.edu
License
This project is licensed under the terms of the public domain license associated with the dataset from Booking.com.

Acknowledgments
Special thanks to the University of Illinois at Urbana-Champaign for supporting this project.

Feel free to reach out to any of the contributors for more information or with any questions regarding the project.
