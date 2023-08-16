# SAST-AGENT

## Problem definition:

The objective of the project revolves around leveraging the capabilities of both Desktop-based and Cloud-based Static Application Security Testing (SAST) tools. The project entails the development of an AI agent intended to bolster the effectiveness of security analysis procedures. The primary emphasis is placed on the detection and resolution of False Positives (FPs), False Negatives (FNs), and instances of redundancy within ASoC (AppScan for Cloud) reports.

By adopting this strategy, the AI agent serves the dual purpose of optimizing the utilization of developer time, through the efficient management of vulnerability rectifications, while also ensuring meticulous classification. This precision eliminates the possibility of human-induced errors, thereby enhancing the overall integrity of the analysis process.

## Outline of solution: 

The data source utilized in this project consists of SAST scan reports generated through the ASoC tool. These initial reports undergo analysis to eliminate non-essential components, including specific columns, while also identifying and labeling duplicate samples, false positives (FPs), and false negatives (FNs). The involvement of Watson becomes evident as the labeled dataset is imported, and an assessment of class percentages is conducted. Due to the presence of multiple output variables, distinct classes for each of these variables need to be established.

To achieve this, all feasible combinations of classes across the various output variables are identified, and the frequency of these occurrences is tracked to establish the percentages of these class combinations. This methodology assists in recognizing recurring patterns in SAST reports, which are frequently dominated by a higher number of duplicates, FPs, and FNs compared to true positives (TPs). To counteract this imbalance, the dataset is balanced by oversampling the minority combinations randomly. As a result of this process, a well-balanced dataset is created, encompassing an equal number of samples for each combination of output classes.

Continuing onward, a multi-output, multi-classifier model is defined. Given that textual data holds more significance within the dataset than numerical data, the generation of text-to-word frequency vectors is achieved through TF-IDF vectorization. Additionally, categorical variables are encoded numerically using one-hot encoding. By integrating text and numerical features, the foundation for a multi-class, multi-output classifier is established. The random forest classifier undergoes meticulous fine-tuning via hyperparameters obtained from a grid search. This classifier, integrated with the multi-output classifier wrapper, enables the process of multi-class, multi-output classification. Subsequently, the trained classifier is leveraged to predict outcomes on test data. The assessment of model performance entails the utilization of evaluation metrics such as accuracy, F1-Score, Hamming loss, and Jacquard Similarity.

The enhanced model is published on GitHub through the Watson platform, and automated continuous integration is facilitated by Jenkins. The raw ASoC reports can be introduced into the Jenkins job directly or via GitHub. Both of these options have been successfully implemented.

## Architecture:
![image](https://github.com/shibil-rahman/SAST-AGENT/assets/60704318/07a56a3a-6f94-4767-a50a-f210b2960a46)


## Demo Video:

## Link to any other resources:
Mural : 
