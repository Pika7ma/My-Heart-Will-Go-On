# My-Heart-Will-Go-On
Titanic Competition for Kaggle.

## Benchmark

0.82775

## Method

### Feature Engineering

1. Extract 'Title' and 'LastName' from 'Name'.
2. Combine 'SibSp' and 'Parch' together to 'FamMem' (family member), add new feature 'Alone'.
3. Only preserve info of 'Cabin' that sb has cabin or not, discard the detailed cabin info.
4. Family members share same 'LastName' and 'Fare', add new feature 'FamSurvived' indicates if there is a family member survived.
5. Drop 'Name', 'LastName', 'SibSp', 'Parch', 'Ticket'.
6. Change feature representation to numerical.
7. Fill missing values in 'Age' according to 'Pclass' and 'Sex' (may correlated) and represent 'Age' by age band.
8. Fill missing values in 'Fare' by mean (only for test set) and represent 'Fare' by fare band.

### Model Training

Use random forest classifier with grid-searched parameters.

## To-dos

1. Well-designed model ensembling and stacking. Current fine-tuned random forest classification result is better than simple emsembling many models.
2. Check if current features are redundant, or we need to artificially create new features (e.g., group feature extraction, see reference 4).
3. Plot learning curve for model checking.

## References

1. https://www.kaggle.com/startupsci/titanic-data-science-solutions
2. https://www.kaggle.com/arthurtok/introduction-to-ensembling-stacking-in-python
3. https://www.kaggle.com/konstantinmasich/titanic-0-82-0-83
4. https://www.kaggle.com/shunjiangxu/blood-is-thicker-than-water-friendship-forever
5. https://blog.csdn.net/guoxinian/article/details/73740746