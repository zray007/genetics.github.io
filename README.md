# Machine Learning and Genetic Diseases

# Introduction
Life’s foundation is reproduction—genetic information passed down with small changes. Over time, mutations have shaped human evolution, sometimes leading to beneficial adaptations while others cause genetic diseases.
Genetic disorders affect 2% to 5% of all childbirths are diagnosed with genetic disorders that may lead to 5% to 50% of deaths in the childhood [2] and can be inherited, arise spontaneously, or be influenced by environmental factors. Cystic fibrosis, caused by CFTR mutations, is an autosomal recessive disorder requiring both parents to be carriers. In contrast, mutations like p53, linked to cancer, may occur spontaneously. Some conditions, like type 2 diabetes, develop due to external factors such as diet or prenatal substance exposure.
## Dataset
Our project analyzes 22,000 young patients with genetic disorders, categorizing key features into hereditary, spontaneous mutations, and epigenetic influences to investigate their impact.
1. Genes in Mother’s Side - Defect inherited from mother (Hereditary)
2. Inherited from Father - Defect inherited from father (Hereditary)
3. Maternal Gene - Defect from paternal lineage (Hereditary)
4. Paternal Gene - Defect from maternal lineage (Hereditary)
5. Follow-Up - Doctor visit frequency (Condition severity) (Neither)
6. Gender - XX or XY chromosomes (Hereditary)
7. Birth Asphyxia - Oxygen deprivation at birth (Epigenetic)
8. Place of Birth - Socioeconomic indicator (Epigenetic)
9. Folic Acid Levels - Essential for DNA synthesis (Epigenetic & Spontaneous Mutation)
10. H/O Serious Maternal Illness - Birth complications (Epigenetic)
11. H/O Radiation Exposure - X-ray exposure history (Spontaneous Mutation)
12. H/O Substance Abuse - Drug addiction history (Epigenetic)
13. Assisted Conception - Infertility treatment type (Epigenetic & Spontaneous Mutation)
14. No. of Previous Abortions - Prior pregnancy genetic issues (Hereditary)
15. Birth Defect - Congenital abnormality (Hereditary)

# Problem Definition:
In healthcare, “models can provide automated prediction, as well as can perform assistive roles for medical experts” [1]. Using machine learning models in predicting genetic diseases have proven to “have increased predictive capabilities for the risk of complex diseases” compared to other risk assessment tests such as polygenic risk scores. [2] Identifying genetic alterations helps doctors tailor treatments for better long-term effectiveness. Understanding the cause of a patient’s disorder aids in precision and preventative medicine, allowing for personalized care and potential disease prevention through targeted treatments based on an individual’s genetic profile. 

# Methods:
## Preprocessing:
- K-Nearest Neighbors Imputation:
sklearn.impute.KNNImputer can be used for fields like Blood Cell Count, White Blood Cell Count if they are missing.
- Handling Misspellings and Abbreviations:
Fields like Parental Consent and Birth Asphyxia may need fuzzywuzzy for misspellings and MedSpacy for standardization.
- Word Embeddings:
BERT can transform ostensibly useless data into meaningful data, like location of birth.

## Models:
Random Forest:
- sklearn.ensemble.RandomForestClassifier can create an ensemble model capable of finding relationships, though not as deep or recursive as those in a neural network.

Neural Network:
- PyTorch can be used to build deep Neural Networks capable of finding more intricate relationships.

K-Means Clustering (Unsupervised Model):
- sklearn.cluster.KMeans can cluster patients by health conditions and risk factors, providing information about key attributes and potentially aiding other models, despite its limitations.
- Using K-means would be useful in our case since “Unsupervised learning algorithms are especially useful to detect patterns in data sets that have large amounts of data points” [3]

# Results and Discussion
- Accuracy, Precision, Recall, and F1-score are standard ML metrics, but in medical data, minimizing false negatives is our priority
- Silhouette Score - This metric is the standard one for gauging how well a clustering algorithm, in our case K-Means, performed. 
- AUC-ROC Curve - This will help figure out how well the model differentiates between different disorders.

# Goals:
- Create an accurate machine learning model and also gather information about the genetic disorders that can help researchers
- To keep the models lightweight for and for sustainability, not excessively overusing LLMs
- It is important that our model does not output biased results where it is more accurate toward a specific gender or race

Given the nature of genetics we predict the Neural Network will do the best, with the Random Forest possibly lacking the necessary robustness for this task. The clustering might highlight a few important attributes, but may struggle to convey the full picture.

# References
[1] A. Raza et al., “Predicting Genetic Disorder and Types of Disorder Using Chain Classifier Approach,” Genes, vol. 14, no. 1, p. 71, Dec. 2022, doi: https://doi.org/10.3390/genes14010071.

[2] “Advances in Distributed Computing and Artificial Intelligence Journal : 9, Regular Issue 1, 2020,” Advances in Distributed Computing and Artificial Intelligence Journal. - Quadrimestrale = Four-monthly, vol. 9, regular issue, no. 1, pp. 1–120, Feb. 2025, Accessed: Feb. 21, 2025. [Online]. Available: https://www.torrossa.com/en/resources/an/5010975

[3] S. Rauschert, K. Raubenheimer, P. E. Melton, and R. C. Huang, “Machine learning and clinical epigenetics: a review of challenges for diagnosis and classification,” Clinical Epigenetics, vol. 12, no. 1, Apr. 2020, doi: https://doi.org/10.1186/s13148-020-00842-4.
