# predPhogly-Site

Post-translational modification (PTM) involves covalent modification after the biosynthesis process and plays an essential role in the study of cell biology. Lysine phosphoglycerylation, a newly discovered reversible type of PTM that affects glycolytic enzyme activities, and is responsible for a wide variety of diseases, such as heart failure, arthritis, and degeneration of the nervous system. Our goal is to computationally characterize potential phosphoglycerylation sites to understand the functionality and causality more accurately. In this study, a novel computational tool, referred to as predPhogly-Site, has been developed to predict phosphoglycerylation sites in the protein. It has effectively utilized the probabilistic sequence-coupling information among the nearby amino acid residues of phosphoglycerylation sites along with a variable cost adjustment for the skewed training dataset to enhance the prediction characteristics. It has achieved around 99% accuracy with more than 0.96 MCC and 0.97 AUC in both 10-fold cross-validation and independent test. Even, the standard deviation in 10-fold cross-validation is almost negligible. This performance indicates that predPhogly-Site remarkably outperformed the existing prediction tools and can be used as a promising predictor, preferably with its web interface at http://103.99.176.239/predPhogly-Site.


This repository contains the predictive decision-making workflow of predPhogly-Site. 

## Cross-Validation 
Contains the benchmark dataset and the source code of the 10 times 10-fold cross-validation. 
The 10-iterations of 10-fold cross-validation were performed according to the following steps:

  Step 1: Extract the sequence-coupled features from the segmented sequences.

  Step 2: Divide the extracted dataset randomly into 10 disjoint sets.

  Step 3: Select 1 set as test set and utilize the remaining 9 sets as training set.

  Step 4: Train the RBF kernel based SVM predictor with the training set using the optimal hyperparameters (C, gamma) of the respective iteration.

  Step 5: Perform prediction on the test set.

  Step 6: Repeat steps 2 to 5 until all 10 sets had been used for testing.

  Step 7: Merge the prediction outputs and measure the performance.

  Step 8: Repeat steps 1 to 7 for 10 times.

  Step 9: Measure the average performance of 10 repetitions with corresponding standard deviations.




## Independent Test 
Contains the independent test dataset and the predicted and test labels with corresponding prediction performances of the respective predictors.
