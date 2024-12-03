# Heart-Disease-Prediction

**Question/Topic**

Can we build a predictive model to identify individuals at high risk of heart disease using patient data, and what are the most significant predictors of heart disease in this data set?

**Motivation**

Heart disease is a leading global health concern, responsible for significant mortality and morbidity. This data set offers an opportunity to address real-world problems by analyzing patient information to predict heart disease risk. By building an effective predictive model, we can enable early detection and prevention and personalized care.

**The Data set**

We analyzed the Data of Patients ( For Medical Field ) data set in Kaggle <https://www.kaggle.com/datasets/tarekmuhammed/patients-data-for-medical-field>.

**Challenges**

1.  The dataset exhibits a significant imbalance, with 224,429 observations for "No Heart Attack" compared to only 13,201 for "Had Heart Attack." This imbalance can hinder the performance of predictive models, as they may become biased toward the majority class, leading to poor sensitivity for detecting heart attack cases.

2.  When trying to predict whether a person had a heart attack, we found that the variable 'Had Angina' had a high predictive accuracy of 0.73. This suggests that the feature is potentially providing redundant, which could influence the model if not handled properly.

3.  The dataset has a large number of rows (237,630) and 35 variables (columns), leading to challenges with computational efficiency, overfitting, and the potential for irrelevant or noisy features to dilute the model's predictive power.

**How did you overcome the challenges?**

1.  To address the class imbalance, we employed downsampling techniques. This involves reducing the number of samples from the majority class ("No Heart Attack") to match the minority class ("Had Heart Attack"), thereby balancing the class distribution. This approach helps prevent the model from being biased toward the majority class and improves its ability to detect heart attack cases.

2.  To avoid overfitting and ensure the model is not overly influenced by 'Had Angina', we performed feature selection and examined the correlation between variables.

3.  To handle the large number of features and avoid overfitting, we applied techniques such as feature selection and sampling techniques to create a more manageable subset of the data for training.

**What packages were needed for your analysis?**

-   `readxl`: Used for reading and importing Excel files into R.
-   `ggplot2`:Essential for creating data visualizations such as histograms, scatter plots, and bar charts.
-   `pheatmap`: Utilized for creating heatmaps, especially useful for visualizing correlation matrices.
-   `dplyr`: For data manipulation (filtering and grouping).
-   `reshape2`: To reshape data.
-   `randomForest`: To implement Random Forest Regression for Variable Importance.
-   `varImp`: To assess variable importance.
-   `caret`: To build predictive models, data splitting, training and validation.
-   `cluster`: To perform hierarchical clustering.
-   `dendextend` - Used for visualizing dendograms created during hierarchical clustering.

**Discussion: What did you learn from this experience?**

From this experience, we learned the importance of performing Random Forest Regression for variable importance before fitting a Logistic Regression Model. The Random Forest method helped us identify which variables contributed most to predicting heart attacks, providing valuable insights. Additionally, hierarchical clustering allowed us to better understand the relationships between features and how they grouped in the data.

Regarding the dataset, we observed that fitting the model with all the variables gave us an accuracy of 0.79. However, the model's performance did not change significantly when we fitted it with only the most 5 important variables.

-   Accuracy with 'HadAngina': 0.73
-   Accuracy without 'HadAngina': 0.75
-   Accuracy of Top 5 variables without 'HadAngina'(AgeCategory, ChestScan, HadStroke, HadDiabetes, GeneralHealth): 0.72

This demonstrates that while 'HadAngina' is a strong predictor, other variables still contribute meaningfully to the model's overall predictive power.

Additionally, after performing hierchical clustering, we noticed that Cluster 4 had the highest proportion of heart attack cases and features in the cluster included: most individual had ChestScan, majority did not have a stroke but experienced difficulty in walking, and HadAngina and AgeCategory were key features.

**What more could you do with this project in the future?**

In the future, there are two directions to explore:

-   We could apply more advanced clustering techniques or adjust the number of clusters to see if any additional insights can be gained about the different patient groups.
-   Experimenting with deep learning techniques could improve prediction accuracy by using complex relationships between variables.
