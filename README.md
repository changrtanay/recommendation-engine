# recommendation-engine

## Overview
This project is a **Product Recommendation System** that utilizes different recommendation techniques, including:

- **Rating-based Recommendations** (Trending Products)
- **Content-based Recommendations** (User Preferences & Item Similarities)
- **Collaborative Filtering** (User-Item Similarity)
- **Hybrid Recommendations** (Combining Content-Based & Collaborative Filtering)

It is built using **Python** and leverages popular libraries such as **pandas, numpy, scikit-learn, matplotlib, seaborn, and spaCy**.

---

## Features
1. **Data Loading & Preprocessing**
   - Reads a dataset (TSV format) containing product reviews.
   - Cleans missing values and standardizes column names.
   - Extracts relevant features and creates tags for content-based filtering.

2. **Exploratory Data Analysis (EDA)**
   - Computes basic statistics (e.g., number of users, items, and ratings).
   - Visualizes distributions of user interactions and product popularity.
   - Generates heatmaps to analyze rating patterns.

3. **Recommendation Algorithms**
   - **Rating-based Recommendations:** Identifies trending products based on average ratings.
   - **Content-based Recommendations:** Uses **TF-IDF Vectorization** & **Cosine Similarity** to suggest similar products based on descriptions.
   - **Collaborative Filtering:** Identifies similar users and recommends items using **User-Item Matrix & Cosine Similarity**.
   - **Hybrid Recommendations:** Merges content-based and collaborative filtering methods to improve suggestions.

---

## Installation
### Prerequisites
Ensure you have Python installed along with the following libraries:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn spacy
```
Additionally, download the **spaCy English model**:
```bash
python -m spacy download en_core_web_sm
```

---

## Usage
### Step 1: Load Dataset
Replace `'marketing_sample_for_walmart_com-walmart_com_product_review__20200701_20201231__5k_data.tsv'` with your dataset file.
```python
train_data = pd.read_csv('your_dataset.tsv', sep='\t')
```

### Step 2: Run Recommendation Functions
#### **Rating-based Recommendation**
```python
rating_base_recommendation.head(10)
```

#### **Content-based Recommendation**
```python
item_name = 'Example Product Name'
content_based_rec = content_based_recommendations(train_data, item_name, top_n=8)
print(content_based_rec)
```

#### **Collaborative Filtering Recommendation**
```python
target_user_id = 4
collaborative_filtering_rec = collaborative_filtering_recommendations(train_data, target_user_id)
print(collaborative_filtering_rec)
```

#### **Hybrid Recommendation**
```python
target_user_id = 10
item_name = 'Example Product Name'
hybrid_rec = hybrid_recommendations(train_data, target_user_id, item_name, top_n=10)
print(hybrid_rec)
```

---

## Dataset
The dataset should contain at least the following columns:
- `Uniq Id`
- `Product Id`
- `Product Rating`
- `Product Reviews Count`
- `Product Category`
- `Product Brand`
- `Product Name`
- `Product Image Url`
- `Product Description`
- `Product Tags`

---

## Visualization Examples
- Heatmaps of user ratings
- Distribution of user interactions
- Most popular products by rating

---

## Future Improvements
- Implementing **deep learning-based recommendations** (Neural Collaborative Filtering)
- Adding **real-time recommendations** based on user activity
- Incorporating **more advanced NLP techniques** for better content-based filtering

---

## Contributing
Feel free to fork this repository, submit issues, or contribute to improve the recommendation engine.

---

## License
This project is licensed under the MIT License.

