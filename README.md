# Bean-Classification-ML

## Deliverable 1: Initial Prompt
I am doing a machine learning project where the goal is to predict the variety of a dry bean based on its geometric measurements. I have a spreadsheet with columns: ‘Area’, ‘Perimeter’, ‘MajorAxisLength’, ‘MinorAxisLength’, ‘AspectRation’, ‘Eccentricity’, ‘ConvexArea’, ‘EquivDiameter’, ‘Extent’, ‘Solidity’, ‘roundness’, ‘Compactness’, and several ‘ShapeFactors’. There are 13,611 rows. I will ask for Python scikit-learn code soon, but first what is the best way to model this data set?

## Deliverable 2: Why Random Forest?
"Think of a Random Forest as a "committee" of experts." -Gemini

Instead of one single Decision Tree looking at the bean data and making a guess, a Random Forest creates hundreds of trees. Each tree gets a slightly different version of the data. They all vote on whether the bean is a "Sira," "Barbunya," etc., and the majority vote wins.
- Robustness: "It’s hard to "fool" a whole forest." This means a larger dataset is more accurate and will sort out when there are outlier results allowing for more               accurate result.
- Correlated Data: "The instructions mentioned bean measurements are highly correlated." For this specific problem the parameters are closely related which makes it             harder to differentiate between different types of beans. Random Forests handle this much better than other basic models.

## Deliverable 3: First Iteration
<img width="1660" height="1384" alt="confusion_matrix_1" src="https://github.com/user-attachments/assets/76674b55-dec0-4c1c-b484-bec0a8c64303" />

<img width="875" height="484" alt="classification_matrix_1" src="https://github.com/user-attachments/assets/2e19472c-aaec-4b01-9d58-6bcc5db38821" />

-While the model was 93% accurate overall, it only correctly identified 88% of the Sira beans (Recall). Looking at the confusion matrix, we can see many Sira beans were misclassified as Dermason and vice versa.
-Its also interesting to note that the bombay bean was precise 100% of the time. I don't know what a bombay bean looks like but it must have very uniquely distinct parameters from the other beans.

## Deliverable 4: Improved Model
Gemini Suggested things that could be changed to help with the precision for the confusion matrix:
- n_estimators:	The number of trees in the forest. ->	Try changing 100 to 200 or 500.
- max_depth:	How deep each tree can grow. ->	Try setting max_depth=10 or max_depth=20.
- min_samples_split:	The minimum number of data points needed to split a branch. ->	Try min_samples_split=5.

<img width="1566" height="1371" alt="confusion_matrix_2" src="https://github.com/user-attachments/assets/1f4d4085-231a-4069-b03f-bfac82f896ea" />

<img width="875" height="468" alt="classification_matrix_2" src="https://github.com/user-attachments/assets/13d15c1b-f8f3-4645-a298-def47591fd93" />

In the second version, I increased the number of trees (n_estimators) from 100 to 500 and set a max_depth of 15 to see if it would help the model catch more patterns. This seems to have made it only slightly more accurate than before.

## Deliverable 5: Feature Importance
<img width="1925" height="1085" alt="feature_importance_plot" src="https://github.com/user-attachments/assets/55fb1eed-3b14-4b94-b339-69af0f213fe5" />
It looks like the model relies heavily on shapfactors 1 and 3, but relies least on things like "Extent", "Solidity", and shapefactors 2 and 4.
---
## References
* Koklu, M., and Ozkan, I. A. (2020). "Dry Bean Dataset." UCI Machine Learning Repository. https://doi.org/10.24432/C50S4B.
* Duo, P., et al. "UCI Machine Learning Repository." University of California, Irvine, School of Information and Computer Sciences.
