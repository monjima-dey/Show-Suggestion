

# Netflix Show Recommender System

This project is a **content-based recommender system** for Netflix shows and movies.  
It uses **multi-feature TF-IDF vectorization** (genres, cast, director, type, and description) combined with **cosine similarity** to suggest similar titles.  
A **Streamlit** web app is included to allow users to interactively select a show and get recommendations.

***

## 🚀 Features
- **Data Cleaning & Preprocessing**
  - Lowercasing and removing extra spaces in column names.
  - Filling missing values in `listed_in`, `cast`, `director`, and `description`.
- **Feature Engineering**
  - **TF-IDF Vectorization** for:
    - Genres (`listed_in`)
    - Description
    - Cast
    - Director
    - Type (Movie/TV Show)
  - **MultiLabelBinarizer** encoding for genres, cast, and director.
  - Combination of sparse feature matrices into a single feature vector for each title.
- **Similarity Calculation**
  - Cosine similarity between all items in the dataset.
- **Recommendation Function**
  - Retrieves top 10 most similar shows to a given selected title.
- **Web App**
  - Built with Streamlit for interactive recommendations.

***

## 🛠️ Tech Stack
- **Python 3**
- **NumPy** & **Pandas** – Data processing  
- **Scikit-learn** – TF-IDF vectorization, MultiLabelBinarizer, cosine similarity  
- **SciPy** – Sparse matrix operations  
- **Streamlit** – Interactive web interface  
- **LocalTunnel** – Expose the app publicly when running in Colab

***

## 📂 Dataset
The system uses the public **Netflix Titles Dataset** (`netflix_titles.csv`).  
Columns used include:
- `title`
- `listed_in` (genres/categories)
- `cast`
- `director`
- `description`
- `type` (Movie or TV Show)

***

## ⚙️ How It Works
1. **Load and Preprocess Data**
   - Clean and tokenize text features.
2. **Encode Features**
   - Use TF-IDF for text-like features.
   - Use MultiLabelBinarizer for multiple categorical features.
3. **Combine into a Single Sparse Matrix**
4. **Calculate Cosine Similarity Matrix**
5. **Get Recommendations**
   - Find the most similar titles based on user input.
6. **Web Interface**
   - Select a show → Get 10 recommendations.

***

## 💻 How to Run Locally

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/netflix-recommender.git
cd netflix-recommender
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

Example `requirements.txt`:
```
pandas
numpy
scikit-learn
scipy
matplotlib
seaborn
streamlit
```

### 3. Run the app
```bash
streamlit run app.py
```

***

## 🌐 Running in Google Colab
Since Colab doesn't host Streamlit directly, the notebook uses **LocalTunnel** to expose the app:
1. Install `streamlit` and `localtunnel` in Colab.
2. Save the app code to `app.py`.
3. Start the app in background using `nohup`.
4. Expose port `8501` via:
```bash
npx localtunnel --port 8501
```
5. Visit the generated URL.

***

## 📷 Screenshots
**Streamlit Interface Example:**
```
[ Select a Show: Stranger Things ]
--> Get Recommendations
 Recommended Shows:
 - Dark
 - The OA
 - Black Mirror
 ...
```

***

## 📌 Future Improvements
- Combine with collaborative filtering for hybrid recommendations.
- Add popularity metrics.
- Deploy on Streamlit Cloud or Hugging Face Spaces.
- Include cover images and additional metadata.

***


If you want, I can also prepare a **shorter README** with just quick-start instructions and a screenshot section, so it's GitHub-friendly.  

Do you want me to generate that shorter version too?

[1] https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/93363665/f5e56ae9-045a-4b31-ba95-3ec7ea8ab830/Project.ipynb
