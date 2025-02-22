# Machine Learning and Genetic Diseases
# Proposal Video

# Introduction
Life’s foundation is reproduction—genetic information passed down with small changes. Over time, mutations have shaped human evolution, sometimes leading to beneficial adaptations while others cause genetic diseases. Genetic disorders affect 2% to 5% of all childbirths are diagnosed with genetic disorders that may lead to 5% to 50% of deaths in the childhood [2] and can be inherited, arise spontaneously, or be influenced by environmental factors [3, 4]. Cystic fibrosis, is an autosomal recessive disorder requiring both parents to be carriers [5]. In contrast, mutations like p53, linked to cancer, may occur spontaneously [6]. Some conditions, like type 2 diabetes, develop due to external factors such as diet or prenatal substance exposure [7].
## Dataset
Our project analyzes 22,000 young patients with genetic disorders, categorizing key features into hereditary, spontaneous mutations, and epigenetic influences to investigate their impact.
1. Genes in Mother’s Side - Hereditary
2. Inherited from Father - Hereditary
3. Maternal Gene - Hereditary
4. Paternal Gene - Hereditary
5. Follow-Up - Neither
6. Gender - Hereditary
7. Birth Asphyxia - Epigenetic
8. Place of Birth - Epigenetic
9. Folic Acid Levels - Epigenetic & Spontaneous Mutation
10. H/O Serious Maternal Illness - Epigenetic
11. H/O Radiation Exposure - Spontaneous Mutation
12. H/O Substance Abuse - Epigenetic
13. Assisted Conception - Epigenetic & Spontaneous Mutation
14. No. of Previous Abortions - Hereditary
15. Birth Defect - Hereditary

# Problem Definition:
In healthcare, “models can provide automated prediction, as well as can perform assistive roles for medical experts” [1]. Using machine learning models in predicting genetic diseases have proven to “have increased predictive capabilities for the risk of complex diseases” compared to other risk assessment tests such as polygenic risk scores. [2] Understanding the cause of a patient’s disorder aids in precision and preventative medicine, allowing for personalized care and potential disease prevention through targeted treatments based on an individual’s genetic profile. We want to create a model that can predict an individual's risk of certain genetic diseases based on the given factors and find possible associated causes for genetic diseases.

# Methods:
## Preprocessing:
K-Nearest Neighbors Imputation:
- sklearn.impute.KNNImputer can be used for fields like Blood Cell Count, White Blood Cell Count if they are missing.

Handling Misspellings and Abbreviations:
- Fields like Parental Consent and Birth Asphyxia may need fuzzywuzzy for misspellings and MedSpacy for standardization.

Word Embeddings:
- BERT can transform ostensibly useless data into meaningful data, like location of birth.

## Models:
Random Forest:
- sklearn.ensemble.RandomForestClassifier can create an ensemble model capable of finding relationships, though not as deep or recursive as those in a neural network.

Neural Network:
- PyTorch can be used to build deep Neural Networks capable of finding more intricate relationships.

K-Means Clustering (Unsupervised Model):
- sklearn.cluster.KMeans can cluster patients by health conditions and risk factors, providing information about key attributes and potentially aiding other models, despite its limitations.
- Using K-means would be useful in our case since “Unsupervised learning algorithms are especially useful to detect patterns in data sets that have large amounts of data points” [3]

# Results and Discussion
Accuracy, Precision, Recall, and F1-score are standard ML metrics, but in medical data, minimizing false negatives is our priority

Silhouette Score - This metric is the standard one for gauging how well a clustering algorithm, in our case K-Means, performed. 

# Goals:
Create an accurate machine learning model and also gather information about the genetic disorders that can help researchers and medical professionals.

Given the nature of genetics we predict the Neural Network will do the best, with the Random Forest possibly lacking the necessary robustness for this task. The clustering might highlight a few important attributes, but may struggle to convey the full picture.

# References
[1] A. Raza et al., "Predicting Genetic Disorder and Types of Disorder Using Chain Classifier Approach," Genes, vol. 14, no. 1, p. 71, Dec. 2022. [Online]. Available: https://doi.org/10.3390/genes14010071

[2] “Advances in Distributed Computing and Artificial Intelligence Journal : 9, Regular Issue 1, 2020,” Advances in Distributed Computing and Artificial Intelligence Journal. - Quadrimestrale = Four-monthly, vol. 9, regular issue, no. 1, pp. 1–120, Feb. 2025. [Online]. Available: https://www.torrossa.com/en/resources/an/5010975

[3] J. Zarocostas, "Serious birth defects kill at least three million children a year," BMJ, vol. 332, no. 7536, p. 226, Feb. 2006. [Online]. Available: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1360426/

[4] S. Rauschert, K. Raubenheimer, P. E. Melton, and R. C. Huang, "Machine learning and clinical epigenetics: a review of challenges for diagnosis and classification," Clinical Epigenetics, vol. 12, no. 1, Apr. 2020. [Online]. Available: https://doi.org/10.1186/s13148-020-00842-4

[5] M. S. Castellani et al., "Cystic Fibrosis-Related Diabetes (CFRD): Overview of Associated Genetic Factors," International Journal of Molecular Sciences, vol. 22, no. 6, p. 3136, Mar. 2021. [Online]. Available: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8005125/

[6] M. G. Goggins et al., "Genetics and Genetic Testing in Pancreatic Cancer," Gastroenterology, vol. 149, no. 3, pp. 676–689, Sep. 2015. [Online]. Available: https://www.gastrojournal.org/article/S0016-5085(15)01089-6/fulltext

[7] A. T. Hattersley and S. Ellard, "Monogenic Diabetes: What It Teaches Us on the Common Forms of Diabetes," Endocrine Reviews, vol. 37, no. 3, pp. 190–222, Jun. 2016. [Online]. Available: https://academic.oup.com/edrv/article/37/3/190/2354693
