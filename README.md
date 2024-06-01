Predict survival on the Titanic using machine learning algorithms based on passenger data.

# Titanic Survival Prediction

The provided repository hosts a script designed to forecast passenger survival rates aboard the Titanic utilizing a Support Vector Machine (SVM) model. It leverages the renowned Titanic dataset sourced from Kaggle for this purpose.
## Dataset

The dataset includes various details about the passengers, such as age, sex, fare, and other relevant variables. The target variable is "Survived," indicating whether a passenger survived (1) or did not survive (0).

## Preprocessing Steps

1. **Fill Missing Values**:
   - `Age`: Filled with the median age.
   - `Embarked`: Filled with the mode (most common value).
   
2. **Drop Column**:
   - `Cabin`: Dropped due to many missing values.
   
3. **Convert Categorical to Numerical**:
   - `Sex`: Converted to numerical values (male -> 0, female -> 1).
   - `Embarked`: Applied one-hot encoding.

4. **Feature and Target Variable**:
   - Features (`X`): All columns except `Survived`, `Name`, `Ticket`, and `PassengerId`.
   - Target (`y`): The `Survived` column.

5. **Data Splitting**:
   - The data is split into training (80%) and testing (20%) sets.

6. **Standardization**:
   - Features are standardized to have mean 0 and variance 1.

## Model Training

A Support Vector Machine (SVM) model is trained using the standardized training data.

## Model Evaluation

The model is evaluated on the test set using the following metrics:
- Accuracy
- Precision
- Recall
- F1 Score

## Usage

To predict the survival of a new passenger, run the script and provide the passenger details when prompted.

### Example

```python
new_passenger = {
    'Pclass': 3,
    'Sex': 'male',
    'Age': 22,
    'SibSp': 1,
    'Parch': 0,
    'Fare': 7.25,
    'Embarked': 'S'
}
result = predict_survival(new_passenger)
print("Survived" if result == 1 else "Did not survive")
