# Team DedSec: BRAINDEAD Hackathon Submission
This repository includes the concise report and models of both the problem statements of BrainDead 2k25.

---

## IPL Data Analysis & 2025 Winner Prediction
### Hackathon Submission - Problem Statement 1

### Abstract
This project analyzes historical IPL data (2008-2024) to uncover trends, insights, and key performance indicators. Additionally, it includes building a predictive model to forecast the winner of the 2025 IPL season using machine learning techniques, including ensemble models like Random Forest and XGBoost.

### Project Structure
- `dedsec_brain_dead_2k25.ipynb` - Jupyter Notebook with data processing, EDA, and model training.

- `data/` - Folder containing datasets (matches.csv, deliveries.csv).

- `models/` - Saved models for future predictions.

### Steps Taken
#### 1. Data Cleaning & Feature Engineering

- Handle missing values, outliers, and inconsistencies.

- Extract meaningful features from matches.csv and deliveries.csv.

#### 2. Exploratory Data Analysis (EDA)

- Team and player performance analysis (win rates, batting/bowling stats).

- Seasonal trends (run rates, Orange & Purple Cap holders).

- Visualizations with Matplotlib & Seaborn.

#### 3. Predictive Model for IPL 2025 Winner

- Used ensemble models (Random Forest, XGBoost) and explored neural networks.

- Evaluated using metrics like accuracy and F1-score.

- Provided a discussion on strengths, limitations, and insights.

#### 4. Tools & Technologies
- Data Handling: Pandas, NumPy

- Visualization: Matplotlib, Seaborn

- Machine Learning: Scikit-Learn, XGBoost

- Clustering: K-Means for player classification

- Notebooks: Google Colab

### Conclusion
- Comprehensive Analysis Report with insights & methodology

- Source Code for EDA and IPL winner prediction

- Discussion on Model Performance and prediction results

---

## Research Text Summarization
### Hackathon Submission - Problem Statement 2

### Abstract
This project is on building a summarization model for research papers using extractive-abstractive techniques. The goal was to develop a model that outperforms existing state-of-the-art approaches in research text summarization, evaluated using ROUGE and BLEU scores.

Three datasets were used:
- CompScholar
- ArXiv
- PubMed

The focus was on models that would deliver high-quality summaries while being computationally efficient in order to complete training within the hackathon time.

### Project Structure
- `dedsec_brain_dead_2k25.ipynb` - Jupyter Notebook with data processing, EDA, and model training.
- `data/` - folder containing the CompScholar dataset

### Steps Taken
#### 1. Data Collection
- Loaded the datasets, Hugging Face Datasets library for ArXiv and PubMed and a CSV file for CompScholar.

#### 2. Data Cleaning and Preprocessing
- Standardizing column names for consistency.
- Dropping missing values to avoid errors during training.
- Combining titles and abstracts for ArXiv, since some models rely on full context.

#### 3. Understanding the Data
- Checked the sizes and random samples of the datasets.
- Plotted histograms of text and summary length to get an idea about the data.
- Generated word cloud and top words in each of the datasets.

#### 4. Model Training
- Tried different LLM models and fine-tuned them.
- Compared Rouge and Bleu scores to develop an inference.

### Limitations and Challenges Faced
We were trying to generate a combination of extractive and abstractive methods that could enhance factual consistency. For this, using BERT-based extractive summarization (like BERTSum) before feeding it into BART or PEGASUS could have improved accuracy. However, several system crashes were encountered and memory issues persisted.
- Research papers are long, and running extractive summarization first, BERTSum significantly increased memory usage, making it difficult to process everything efficiently.
- Since extractive models require sentence scoring and selection before feeding the result into abstractive models, the two-step approach increased the computational load.
- Both BERT-based extractive models and transformer-based abstractive models are memory-intensive. Running them back-to-back on large documents without gradient checkpointing or truncation caused system instability.

### Conclusion
This was a challenging but insightful experiment in summarizing research articles efficiently. While BART is the best practical option given time constraints, further fine-tuning and optimization can push the ROUGE and BLEU scores even higher. The next step would be training on domain-specific data and optimizing inference speed for even better results. Also simplifying the extractive step or using lighter models to ensure stability while still improving summary quality is something to be taken into consideration further.
