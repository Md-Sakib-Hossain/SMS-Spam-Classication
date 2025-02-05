### **Summary of SMS Spam Classification Project**

#### **1. Data Import & Preprocessing**
- Dataset: SMS Spam Collection from Kaggle.
- Data consists of 5,572 messages labeled as **spam (1)** or **ham (0)**.
- Encoding applied to labels (`ham → 0`, `spam → 1`).
- Dataset was imbalanced (**747 spam vs. 4825 ham messages**), so oversampling was applied to balance the data.

#### **2. Feature Engineering**
- Extracted features:
  - **Word count**
  - **Contains currency symbols**
  - **Contains numbers**
  - **Message length**
  - **Uppercase word count**
  - **Special character count**
- Visualization: Histograms and count plots were used to analyze distributions.

#### **3. Data Cleaning**
- Removed special characters, stopwords, and short words.
- Applied **lemmatization** for text normalization.
- Used **TF-IDF vectorization** (`max_features=500, ngram_range=(1,2)`) to transform text into numerical features.

#### **4. Model Training & Evaluation**
Three machine learning models were implemented:
1. **Logistic Regression**
   - **Accuracy:** 98.9% (Cross-Validation)
   - **Precision, Recall, F1-score:** ~99%
   
2. **Decision Tree**
   - **Accuracy:** 98.5% (Cross-Validation)
   - **Precision, Recall, F1-score:** ~98%

3. **Random Forest**
   - **F1-score:** 99.7% (Cross-Validation)
   - **Precision, Recall, F1-score:** ~100% (Best performer)

#### **5. Results**
- **Random Forest outperformed Logistic Regression and Decision Tree** in classification accuracy and F1-score.
- **Confusion matrices** showed low false positives and negatives across all models.
- Final model selection: **Random Forest for production use** due to superior performance.
