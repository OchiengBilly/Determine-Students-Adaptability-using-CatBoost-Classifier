# **Students Adaptability to Online Learning**  

## **Project Overview**  
The shift to online learning has highlighted the need to understand students' adaptability to virtual education environments. This project uses **machine learning models** to predict students' adaptability based on various factors such as **internet access, financial conditions, device availability, and institutional support**.  

By leveraging **classification models**, this study helps educators, policymakers, and institutions identify students who may struggle with online learning and take proactive measures to support them.  

## **Dataset**  
The dataset is sourced from **Kaggle** *https://www.kaggle.com/datasets/mitusonia/student-adaptivity-in-online-class* and contains **categorical features** that capture different aspects of a student's learning environment.  

### **Features Used in Training**  
| Feature              | Description  |  
|----------------------|-------------|  
| **Gender**          | Student's gender. |  
| **Age**             | Age group of the student. |  
| **Education Level** | Level of education (e.g., High School, Undergraduate). |  
| **Institution Type** | Public or Private institution. |  
| **IT Student**      | Whether the student is an IT student (Yes/No). |  
| **Location**        | Urban or Rural location. |  
| **Load-shedding**   | Power outages affecting online learning. |  
| **Financial Condition** | Student’s financial stability (Poor, Mid, Rich). |  
| **Internet Type**   | Type of internet connection (Wi-Fi, Mobile Data). |  
| **Network Type**    | Mobile network quality (4G, 3G, etc.). |  
| **Class Duration**  | Average duration of online classes. |  
| **Self LMS**        | Whether the student uses a self-learning management system. |  
| **Device**         | Type of device used for online learning. |  
| **Adaptivity Level (Target Variable)** | Student’s adaptability to online learning. |  

## **Data Preprocessing**  
To ensure the dataset was suitable for machine learning, the following preprocessing steps were applied:  
- **Missing Value Handling**: Checked for missing values and ensured data integrity.  
- **One-Hot Encoding**: Converted all categorical features into numerical representations.  
- **Label Encoding**: Encoded the target variable (**Adaptivity Level**) for model training.  
- **Train-Test Split**: Split the data into **90% training** and **10% testing** to evaluate model performance.  

## **Machine Learning Models and Performance**  
Four machine learning models were trained and evaluated to determine which model best predicts student adaptability:  

| Model                | Accuracy (%) |  
|----------------------|-------------|  
| **Logistic Regression** | 70.24          |  
| **Decision Tree**      | 95.86          |  
| **Random Forest**     | 93.39          |  
| **CatBoost**          | 95.04          |  

- The **Decision Tree model** performed the best with **95% accuracy**.  
- **Random Forest and CatBoost** also achieved high accuracy (**94%**).  
- **Logistic Regression** had lower accuracy (**75%**), suggesting that the relationship between features and adaptability is non-linear.  

## **Evaluation Metrics**  
To assess model performance, the following metrics were used:  
- **Accuracy Score** – Measures overall correctness of predictions.  
- **Confusion Matrix** – Provides insights into classification errors.  
- **Classification Report** – Includes precision, recall, and F1-score for better understanding.  
- **Feature Importance** – Identifies the most influential factors in adaptability prediction.  

## **Hyperparameter Tuning**  
To improve model performance, **GridSearchCV** and **RandomizedSearchCV** were used for hyperparameter tuning. This process helped optimize parameters such as:  
- **Regularization strength (`C`)** for Logistic Regression.  
- **Max depth, min samples split** for Decision Tree and Random Forest.  
- **Learning rate and iterations** for CatBoost.  

## **Feature Importance Analysis**  
Understanding which features impact student adaptability the most is crucial. The **Feature Importance** plot showed that:  
- **Internet Type, Device, and Financial Condition** had the highest impact.  
- **Self LMS and Class Duration** were also significant but less influential.  

## **Making Predictions**  
A **prediction function** was implemented to allow users to input new student data and receive an adaptability prediction.  

Example usage:  
```python
new_student = pd.DataFrame({
    'Gender': ['Male'],
    'Age': ['21-25'],
    'Education Level': ['Undergraduate'],
    'Institution Type': ['Private'],
    'IT Student': ['No'],
    'Location': ['Urban'],
    'Load-shedding': ['Low'],
    'Financial Condition': ['Mid'],
    'Internet Type': ['Wi-Fi'],
    'Network Type': ['4G'],
    'Class Duration': ['2-3 hours'],
    'Self Lms': ['Yes'],
    'Device': ['Laptop']
})

prediction = model.predict(new_student)
print(f"Predicted Adaptability Level: {prediction[0]}")
```

## **Future Improvements**  
To enhance the model’s effectiveness, the following improvements are planned:  
✅ Implement **Deep Learning Models** (e.g., Neural Networks) to capture complex relationships.  
✅ Explore **data augmentation** techniques to improve generalization.  
✅ Integrate **more features** like student engagement metrics or exam performance.  

## **How to Use This Project**  
1. **Install Dependencies**  
   ```bash
   pip install pandas numpy scikit-learn catboost matplotlib
   ```  
2. **Load the dataset** *((https://www.kaggle.com/datasets/mitusonia/student-adaptivity-in-online-class))*  
3. **Run the script** to train models and make predictions.  

## **Conclusion**  
This project provides valuable insights into factors affecting **students' adaptability to online learning**. By leveraging machine learning, institutions and educators can identify at-risk students and offer targeted support to improve their online learning experience.  

---