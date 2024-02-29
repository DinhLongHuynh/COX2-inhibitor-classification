# COX2-inhibitor-classification
During my recent course, I have learned about using the pharmacophore hypothesis to screen a library of 100037 compounds for COX-2 inhibitors. Out of the 1000 most prominent compounds returned, 159 of them were found to be active, resulting in a recall ratio of 67% (the number of actual active compounds is 235). However, the pharmacophore model used only a few known active compounds to generate the hypothesis, so I decided to further develop a classifier using machine learning with that library, to achieve a significantly higher recall.

To achieve this, I used the RDKit library to generate 17 physiochemical descriptions for each compound and removed any highly correlated features to reduce collinearity. I then standardized the data using the StandardScalar function and generated the Morgan Fingerprint of each compound. The data was then split into a training set and a testing set with an 8:2 ratio, and data oversampling was conducted to handle the data imbalance.

I trained three different RandomForestClassifier models based on three different types of features: physiochemical features, Morgan Fingerprint, and a combination of both. The recall of the physiochemical, fingerprint and combined models were 0.77, 0.96, and 0.98, respectively. They all outperformed the pharmacophore hypothesis, with the combined model being the best among them.

