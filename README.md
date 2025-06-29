# 🛍️ Sentiment-Aware Recommendation System with Demand Forecasting

A hybrid fashion recommendation engine that integrates collaborative filtering, sentiment analysis from user reviews, and time-series demand forecasting to deliver smarter, context-aware product suggestions.

## 📌 Project Highlights

- **Sentiment Analysis**: Classifies user reviews to derive deeper insights into product quality beyond star ratings.
- **Demand Forecasting**: Uses Holt-Winters Exponential Smoothing to predict product demand and flag trending or low-stock items.
- **Hybrid Recommendation Engine**: Combines collaborative filtering with sentiment-aware rankings and demand signals for superior personalization.

---

## 💡 Motivation

Traditional recommendation systems overlook user sentiment and ignore future demand. This project tackles that by:
- Mining qualitative insights from reviews.
- Forecasting future demand using time series models.
- Delivering business-aware and user-centric recommendations.

---

## 📁 Datasets Used

1. **Clothing Reviews Dataset**
   - Fields: Customer ID, Purchase Date, Review Text, Rating, etc.
   - Used for: Sentiment classification, collaborative filtering, and demand trend analysis.

2. **Product Metadata Dataset**
   - Fields: Product ID, Brand, Category, Description, etc.
   - Used for: Content-based similarity and product enrichment.

---

## 🔍 Key Modules

### 1. Sentiment Analysis (NLP + ML)
- **Preprocessing**: Cleaning, stopword removal, lemmatization.
- **Vectorization**: TF-IDF.
- **Models Evaluated**:
  - ExtraTreesClassifier (final choice)
  - SVC, Random Forest, Logistic Regression, Naive Bayes, KNN, etc.
- **Metrics**: Accuracy (93.3%), Precision (94.2%), ROC-AUC (0.73)

### 2. Demand Forecasting
- **Model**: Holt-Winters Exponential Smoothing
- **Forecast Horizon**: 6 months
- **Output**:
  - Trending Products
  - Low Stock Alerts
  - Discount Recommendations for low-demand items

### 3. Hybrid Recommendation System
- **Collaborative Filtering**: K-Nearest Neighbors (User-based)
- **Content-Based Filtering**: Review sentiment via ExtraTreesClassifier
- **Scoring**:
  - `Final_Score = 0.6 × Collaborative_Score + 0.4 × Sentiment_Score`
- **UI Hooks**: “Trending Now”, “You May Also Like”, “Low Stock Warning”

---

## 🔢 Sample Output

```json
{
  "CustomerID": 46251,
  "Recommendations": {
    "Hybrid": [
      "Oversized Blazer with Premium Fabric (Adidas)",
      "Oversized Jacket with Stretch Fabric (Zara)"
    ],
    "User-Based": [
      "Acid Wash T-Shirt with Denim Fabric (Levi's)",
      "Ripped Tank Top with Denim Fabric (Levi's)"
    ],
    "Trending_Now": [
      "Distressed T-Shirt with Lightweight Fabric",
      "Printed Dress with Fleece Fabric"
    ]
  }
}
```

---

## 🛠️ Tech Stack

- **Language**: Python 3.9+
- **Libraries**:
  - `scikit-learn`, `pandas`, `matplotlib`, `seaborn`, `statsmodels`, `nltk`
- **Models**: ExtraTreesClassifier, Holt-Winters, Nearest Neighbors

---

## 🚀 How to Run

```bash
# Install dependencies
pip install -r requirements.txt

# Run main script
python app.py
```

> Note: This assumes you have `clothing_reviews.csv` and `product_data.csv` in the root directory.

---

## 🎓 Authors

- [Arkajyoti Sarkar](https://github.com/yourgithub)
- Dipanjan Saha
- Debjit Chatterjee
- Saikat Mukherjee
- Srinjoy Dhar

Under the guidance of **Dr. Lewlisa Saha**, Techno Main Salt Lake.

---

## 📚 References

- Rui et al., *Exploring Consumer Sentiments* [DOI](https://doi.org/10.1016/j.jretconser.2024.104097)
- Chen et al., *Sentiment-Aware Hybrid Models*
- Singh et al., *ARIMA-based Demand Forecasting*
- More in the report: see `/CSE(DS)_report.pdf`

---

## 📈 Future Scope

- Real-time recommendation pipeline with feedback loops.
- Image-based visual similarity using CNNs.
- Geo-personalized fashion recommendations.
- Multilingual sentiment support (Indian languages).
