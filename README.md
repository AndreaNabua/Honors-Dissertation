# AN RS Approach to Predicting the Side Effects of Drugs

## Motivation

#### What are recommender systems?
Recommender systems (RS) are systems that filter through large volumes of information to find the most relevant subset.
#### Recommender Systems in Healthcare 
Health recommender systems (HRS) are now more relevant due to the growing amount of circulating medical information. Amongst HRSs, there
exists a handful of research that use RS in predicting drug side effects (DSE).
#### Why predict DSEs?
DSEs are one of the leading causes of death and disease. Most DSEs are not detected until after it has been deployed into the market. They are the main
causes of failure in drug development, and drug withdrawal. The prediction of DSEs is of interest to improve this expensive process.
#### RS that predict DSEs
It has been observed that similar drugs share similar side effects. Collaborative Filtering (CF) is a type of RS implementation that leverages
similarities. CF can leverage the similarities between drugs to predict potential side effects. There have been efforts to employ CF techniques to
predict the potential side effects of drugs (see Figure 1).

## Goal
This project implements a CF approach to predict DSEs, namely LFM with stochastic gradient descent.
The primary objectives are:
* Implement a collaborative filtering RS approach to predict the drug side effects.
Recommender systems
* Investigate usefulness by comparing it with the other existing methods.

## Background on CF and LFM...
Collaborative filtering works with what is generally known as a utility matrix, in this case, a drug-side effect matrix (See Figure 2). 

**Goal of collaborative filtering in this problem context**: To predict whether the 0s in the matrix are actually 1s, i.e., predict the potential side effects given the known side effects. In practice, this would help predict side effects that could not be detected until after their deployment into the market.

**LFM (Latent factor model) is a type of CF method**, which uses matrix factorization techniques in order to predict the unknown slots (i.e., the 0s) in the matrix.

## Methods
In order to compare against the benchmark models, 2 methodologies were undergone by our proposed model: Galeano’s and Zhang’s methodology (See Figure 3 - left). 2 benchmark models underwent Galeano (Galeano’s model and PPN-Net), while the other 7 underwent Zhang’s methodology.

## Primary Findings
The primary metric of evaluation is the AUPRC, as it better handles data imbalance than AUROC.
* See Figure 4. Our method is more performant than 2 of the first few attempts in research to predict DSE with only phenotypic information (Liu, Pauwel, Mizutani methods). Not as good as the latest models, which are RSs by Zhang.
* See Figure 5. Outperforms Galeano’s method which is also a type of LFM, as well as PPN-Net.
* In terms of the other non-primary metrics, the results raise the question of whether this is a good model. E.g. Our model achieves high recall (99%) at the expense of very low precision (4%) on Galeano’s Dataset.

## Conclusion
One of the limitations of this project is that the system does not yield an appropriate performance, therefore it is questionable if it were to be used in a real-life setting. 
In addition, there could be a possibility of Zhang’s models being much more performant had they used AUROC as the primary metric for model selection. 

## Running instructions
Fork the project and run the notebook. Any required libraries are imported at the top of the notebook.

## References

Zhang, H. Zou, L. Luo, Q. Liu, W. Wu, and W. Xiao, “Predicting potential side effects of drugs by recommender methods and ensemble learning,” Neurocomputing, vol. 173, pp. 979–987, Jan. 2016.

D. Galeano and A. Paccanaro, “A recommender system approach for predicting drug side effects,” in 2018 International joint Conference on Neural Networks (IJCNN), pp. 1–8, 2018.

M. Liu, Y. Wu, Y. Chen, J. Sun, Z. Zhao, X. wen Chen, M. E. Matheny, and H. Xu, “Large-scale prediction of adverse drug reactions using chemical, biological, and phenotypic properties of drugs,” Journal of the American Medical Informatics Association, vol. 19, pp. e28–e35, June 2012.

## Authors
Experiments and code are conducted and written by myself, for my Honors Dissertation.
