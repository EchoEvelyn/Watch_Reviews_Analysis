# Watch Reviews Analysis

This project focuses on analyzing customer reviews of watches using various Natural Language Processing (NLP) techniques. The goal is to extract insights that can help with product improvement, problem identification, and targeted marketing strategies. The analysis covers tokenization, TF-IDF vectorization, K-means clustering, and topic modeling using Latent Dirichlet Allocation (LDA).


## Table of Contents
1. [Data](#data)
2. [Tools and Technologies](#tools-and-technologies)
3. [Installations](#installations)
4. [Findings and Conclusions](#findings-and-conclusions)


## Data
The Amazon Customer Reviews dataset records watch reviews from 04/05/2001 to 08/31/2015. 

**Key Features**: 
- **star_rating**: A numerical rating (from 1 to 5) provided by the customer to reflect their satisfaction with the product.
- **review_body**: The main text of the customer review, containing detailed feedback about the product.
- **review_date**: The date when the customer submitted the review.

You can download the data here: [Download the Data](https://drive.google.com/file/d/1O6lhXvz0AthavxElCZDlFIocZXc0oMT6/view?usp=sharing)



## Tools and Technologies
- **Python**: The main programming language used for data processing and analysis.
- **NumPy**: For numerical computing, including array manipulation.
- **Pandas**: For data manipulation and analysis, particularly for handling data frames.
- **PyDrive**: Used for authenticating and accessing Google Drive to manage file uploads/downloads.
- **Matplotlib & Seaborn**: For data visualization, used to create plots and visual insights.
- **NLTK**: (Natural Language Toolkit) Used for text preprocessing tasks such as tokenization, stopword removal, and stemming.
- **Scikit-learn**: Machine learning library used for:
- **TF-IDF Vectorization**: For transforming text into numerical feature vectors.
- **K-Means Clustering**: For clustering customer reviews.
- **PCA (Principal Component Analysis)**: For dimensionality reduction.
- **Latent Dirichlet Allocation (LDA)**: For topic modeling.
- **Gensim**: Library for topic modeling and document similarity analysis, used to implement LDA and compute topic coherence scores.


## Installations
### Environment Setup

Ensure the following Python libraries are installed:
  
```bash
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import nltk

from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.cluster import KMeans
from sklearn.decomposition import LatentDirichletAllocation, PCA

import gensim
from gensim.corpora import Dictionary
from gensim.models import CoherenceModel

# For NLTK downloads
nltk.download('punkt')
nltk.download('stopwords')
```

### Authenticate with Google Drive:
Since I stored the dataset in Google Drive, I need to authenticate and access it using PyDrive and Google Colab:
```bash
from pydrive.auth import GoogleAuth
from pydrive.drive import GoogleDrive
from google.colab import auth
from oauth2client.client import GoogleCredentials
```
### Laod the Data From Google Drive
The dataset (e.g., watch_reviews.csv) is stored in Google Drive, and we use the file ID to retrieve it:
```bash
# Google Drive file ID
id = 'your_google_drive_file_id_here'

# Download the dataset
file = drive.CreateFile({'id': id})
file.GetContentFile('watch_reviews.tsv')

# Load the dataset into a Pandas DataFrame
df = pd.read_csv('watch_reviews.tsv', sep='\t', on_bad_lines='skip')
```

## Findings and Conclusions
Through the application of K-means clustering and Latent Dirichlet Allocation (LDA), we derived several valuable insights from customer reviews. These insights can be leveraged for product improvement, customer satisfaction, and more effective marketing strategies:

**Key Findings**:
- **Watch as a Gift**: A significant portion of reviews suggest that watches are often purchased as gifts for special occasions such as Valentine's Day, birthdays, and anniversaries. This provides an opportunity to tailor marketing strategies toward gift-giving consumers.

- **Shipping and Returns**: Several reviews mention issues related to shipping delays and return policies. This highlights the need for improvements in logistics and customer service, which could lead to a better customer experience and higher satisfaction rates.

- **Product Quality**: Mixed feedback on product quality was identified, specifically regarding aspects such as the watchband, style, color, and battery life. These issues can be addressed by improving product design or quality control, ultimately reducing negative reviews and returns.

**Conclusions**:
- **Marketing Opportunities**: The insights from customer reviews reveal that focusing on gift-centric marketing campaigns could increase sales, especially around key holidays. Advertising watch products as ideal gifts may attract a broader customer base during these periods.

- **Customer Experience Improvements**: Addressing concerns around shipping and returns could significantly enhance customer satisfaction. By improving logistics and providing better return policies, the company could see fewer negative reviews and improved brand loyalty.

- **Product Enhancement**: By focusing on product quality improvements (e.g., durability of the watchband, battery life), the company can directly tackle some of the most common complaints, leading to higher ratings and fewer returns.
