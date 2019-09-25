# Using an Autoencoder to Identify Credit Card Fraud
*Author: A. Trahan*  
*Date:   August 2019*

An autoencoder is a neural netowrk shaped like an hour glass (narrow in the center) that is trained on its own inputs. The goal is to build a simplified latent representation of the inputs (the narrow part) that can still be reliably expanded back to the original dataset. The model is trained on \"good data\ then when anomalous data is submitted to the model it can't be distilled to latent representation the same way, making it easier to separate.

This notebook uses classic and neural network methods to attempt to discover credit card fraud. The dataset contains 404 features generated from anaonymized data from a German bank using PCA, so feature engineering options are limited.

The process consists of:

* Resampled and split the unbalanced dataset
* Train an SVM as a base model, aiming for ROC_AUC and Recall
* Train an autoencoder
    * Visual inspection of autoencoder
      * Use t-SNE to plot initial data in R2
      * Use t-SNE to plot latent representation in R2
    * Train LogReg on latent representation, aiming for ROC_AUC and Recall
