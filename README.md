#  Detecting Suspicious and Fake Amazon Reviews

##  Project Overview
As e-commerce platforms such as Amazon continue to scale, detecting fraudulent or
manipulated reviews has become increasingly difficult through manual moderation.
This project applies data analytics, natural language processing (NLP), and machine
learning techniques to identify suspicious Amazon reviews based on behavioral,
sentiment, and linguistic patterns.

The goal is not to definitively label reviews as fake, but to detect anomalous and
high-risk review behavior that may indicate coordinated or automated manipulation.

---

##  Business Problem
Fake reviews distort customer trust and decision-making on online marketplaces.
They often originate from bots, incentivized reviewers, or coordinated review
networks and can appear authentic when viewed individually.

This project investigates whether suspicious reviews can be detected using:
- Reviewer posting behavior
- Sentiment extremity and inconsistency
- Linguistic subjectivity and textual patterns

---

## Data Source
- **Dataset:** Amazon Product Reviews  
- **Source:** Kaggle  
- **Size:** ~568,000 reviews  
- **Key Fields:** Review text, rating score, user ID, product ID, timestamp, helpfulness

---

## Tools & Technologies
- Python
- Pandas, NumPy
- Scikit-learn
- NLP (TextBlob, linguistic feature extraction)
- Matplotlib, Seaborn
- Jupyter Notebook

---

## Methodology

### 1. Data Cleaning & Preprocessing
- Removed duplicate reviews
- Validated and corrected helpfulness scores
- Converted Unix timestamps to calendar dates
- Cleaned and standardized review text
- Created behavioral indicators such as:
  - Review length
  - Daily review frequency
  - User-level activity metrics

---

### 2. Feature Engineering
- **Sentiment Polarity:** Measured using TextBlob (–1 to +1)
- **Subjectivity Score:** Identified emotional vs factual language
- **Behavioral Features:** Posting frequency, review length, sentiment consistency
- **Linguistic Analysis:** Detection of generic wording and repetitive patterns

---

### 3. Modeling Approach
Because the dataset lacked ground-truth labels, an unsupervised-to-supervised
pipeline was used:

#### Model A: Behavioral Approach
- K-Means clustering to identify suspicious reviewer groups
- Decision Tree trained on cluster labels
- Accuracy: ~96%
- Strong indicators included sentiment extremity, posting frequency, and review length

#### Model B: Linguistic + Behavioral Approach
- Added subjectivity as a linguistic feature
- Improved detection of emotionally inflated reviews
- Accuracy: ~95%
- Reduced false negatives while maintaining high precision

---

### 4. Validation
- Cross-validation confirmed model stability
- Forensic validation identified duplicated review text posted by multiple users,
  supporting the presence of coordinated or automated behavior

---

## Key Insights
- Suspicious reviewers often post an unusually high number of reviews in a single day
- Fraud-prone reviews exhibit extreme sentiment and high subjectivity
- Fake reviews tend to be shorter, generic, and emotionally exaggerated
- Linguistic features significantly improve fraud detection beyond behavior alone

---
## My Contribution
- Implemented the SingleDayReviewFrequency feature to analyze review patterns.
- Performed sentiment analysis on review data.
- Applied clustering and built a decision tree to derive insights from the reviews.
- Enhanced sentiment analysis by adding a subjectivity feature.
- Ran clustering and decision tree analysis on the updated dataset including subjectivity.
---

## Team Members
- Christie Shin  
- Shivani Vallamdas  
- Gema Zhu  
- Vishal Srivastava  
- Shuai Zhao  

---

## Limitations
- Dataset represents older review behavior and may not capture modern LLM-generated fraud
- No ground-truth labels for fake vs real reviews
- Model is optimized for high-volume and low-effort fraud patterns

---

## Conclusion
This project demonstrates that combining behavioral patterns with sentiment and
linguistic analysis is an effective strategy for identifying suspicious review activity.
The approach provides scalable and interpretable insights that can support automated
fraud detection systems on large e-commerce platforms.

