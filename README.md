# Bean-Classification-ML

## Deliverable 1: Initial Prompt
I am doing a machine learning project where the goal is to predict the variety of a dry bean based on its geometric measurements. I have a spreadsheet with columns: ‘Area’, ‘Perimeter’, ‘MajorAxisLength’, ‘MinorAxisLength’, ‘AspectRation’, ‘Eccentricity’, ‘ConvexArea’, ‘EquivDiameter’, ‘Extent’, ‘Solidity’, ‘roundness’, ‘Compactness’, and several ‘ShapeFactors’. There are 13,611 rows. I will ask for Python scikit-learn code soon, but first what is the best way to model this data set?

## Deliverable 2: Why Random Forest?
"Think of a Random Forest as a "committee" of experts." -Gemini

Instead of one single Decision Tree looking at the bean data and making a guess, a Random Forest creates hundreds of trees. Each tree gets a slightly different version of the data. They all vote on whether the bean is a "Sira," "Barbunya," etc., and the majority vote wins.
- Robustness: "It’s hard to "fool" a whole forest." This means a larger dataset is more accurate and will sort out when there are outlier results allowing for more               accurate result.
- Correlated Data: "The instructions mentioned bean measurements are highly correlated." For this specific problem the parameters are closely related which makes it             harder to differentiate between different types of beans. Random Forests handle this much better than other basic models.

## Deliverable 3:
<img width="1647" height="1403" alt="confusion_matrix_1" src="https://github.com/user-attachments/assets/d2504faf-10ee-4b6f-9a8c-3de4a197fad8" />

<img width="875" height="484" alt="classification_matrix_1" src="https://github.com/user-attachments/assets/2e19472c-aaec-4b01-9d58-6bcc5db38821" />

While the model was 92% accurate overall, it only correctly identified 80% of the Sira beans (Recall). Looking at the confusion matrix, we can see many Sira beans were misclassified as Dermason.
## Deliverable 4:
## Deliverable 5: 
