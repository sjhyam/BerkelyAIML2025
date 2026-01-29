# Bank Marketing Campaign: Comparing Classifiers

## 📊 Overview
This project evaluates multiple machine learning models to predict if a client will subscribe to a bank term deposit based on a telemarketing campaign. The goal is to identify a model that helps the bank optimize its marketing efforts by targeting the right customers.

## 📁 Project Structure
* `comparing_classifiers.ipynb`: Main Jupyter Notebook containing data analysis, cleaning, and modeling.
* `bank-additional-full.csv`: The dataset used for training and testing.
* `CRISP-DM-BANK.pdf`: Background documentation on the data collection and features.
* `README.md`: Project summary and findings.

## 🔍 Summary of Findings
- **Baseline Accuracy:** The dataset is imbalanced; 88.7% of clients said "no." Any model must beat this baseline to be useful.
- **Feature Limitations:** Using only demographic data (age, job, marital status) creates a "performance ceiling." These features alone are not strong enough to predict financial commitment with high precision.
- **Model Comparison:**
    - **Logistic Regression:** Fastest and most interpretable. When balanced, it provides the best utility for identifying potential leads.
    - **Decision Trees:** Highly prone to overfitting unless pruned via `max_depth` tuning.
    - **KNN:** Strong performance but requires careful feature scaling to be accurate.
    - **SVM:** Computationally expensive (slowest training time) without significant accuracy gains over Logistic Regression.

## 💡 Recommendations & Action Items
1. **Model Deployment:** Utilize the **Balanced Logistic Regression** model. While its raw accuracy is lower, it captures more "Yes" outcomes than any other model, providing better ROI for the marketing team.
2. **Data Enhancement:** Future models should incorporate **Social and Economic Indicators** (like the Euribor 3m rate). Analysis shows that the economic environment is a stronger predictor than client demographics.
3. **Targeting Strategy:** Focus resources on clients with a successful `poutcome` (previous campaign success), as historical behavior is the strongest indicator of future subscription.

## 🚀 How to Run
1. Ensure you have `Python 3.10+` installed.
2. Install dependencies:
   ```bash
   pip install pandas scikit-learn seaborn matplotlib
3. Open `comparing_classifiers.ipynb` in **PyCharm** or **Jupyter Lab**.
4. Ensure the dataset `bank-additional-full.csv` is located inside the data/ folder.
5. Run all cells to generate the models and visualizations.

**Course:** Berkeley AI/ML Practical Application III
**Author:** Shyamsunder Mutcha
**GitHub:** [https://github.com/sjhyam](https://github.com/sjhyam)