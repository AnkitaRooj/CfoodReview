# 🍽️ Review Impact Prediction System
## 📋 Project Overview
A comprehensive data science project that predicts how customer reviews impact future product sales using Natural Language Processing (NLP) and machine learning. This system helps businesses understand customer sentiment, quantify review impact, and make data-driven decisions about product management, pricing, and marketing strategies.

[Image](https://github.com/AnkitaRooj/CfoodReview/blob/main/foodRevenueNew.gif)
![Diagram showing the project workflow](https://github.com/AnkitaRooj/CfoodReview/blob/main/foodRevenueNew.gif)

## 🎯 Business Problem
Customer reviews significantly influence purchasing decisions, but their impact on sales is often hard to quantify. This project solves three key challenges:

1. Measuring Review Impact: How much do individual reviews affect sales?

2. Early Warning System: Identifying negative trends before they damage sales

## 🏗️ Architecture
The system follows a two-phase approach:

Phase 1: Sentiment Analysis
* Model: Fine-tuned DistilBERT for sentiment classification

* Classes: Positive (😊), Neutral (😐), Negative (😠)

* Features: Review text analysis with class imbalance handling

* Output: Sentiment labels and confidence scores for all reviews

Phase 2: Impact Prediction
Input: BERT embeddings + metadata features

* Model: Ensemble (Random Forest + Gradient Boosting)

* Target: Composite Impact Score (0-1 scale)

Features:

* Review sentiment (from Phase 1)

* Helpfulness ratio

* Review length and specificity

* Reviewer influence

* Product metadata

* Temporal features

## 🔄 Workflow
Step 1: Data Collection & Preparation
Load review data from CSV/API

Clean and preprocess text data

Engineer features (helpfulness ratio, review length, etc.)

Merge with product metadata

Step 2: Sentiment Analysis (Phase 1)
Fine-tune DistilBERT on review data

Handle class imbalance with weighted loss

Extract BERT embeddings for each review

Predict sentiment with confidence scores

Step 3: Impact Prediction (Phase 2)
Combine BERT embeddings with metadata features

Create composite impact score as target variable

Train ensemble model (Random Forest + Gradient Boosting)

Predict impact scores for all reviews

Step 4: Dashboard Creation
Prepare data for Power BI

Build interactive dashboard with 6 pages

Implement drill-through functionality

Set up automatic data refresh

## 📈 Dashboard Implementation (Power BI)
* Executive Dashboard
1. Menu Health Score: Overall impact metric with trend analysis

2. Products Needing Attention: Early warning system for underperformers

3. Sentiment Health: Real-time sentiment distribution

4. ROI Estimates: Financial impact predictions


* Operations Dashboard
1. Kitchen Efficiency: Prep time vs. customer satisfaction
2. Products Needing Attention : Sales CompositeImpact Score as per Food Product


## 🚀 Business Value
* For Management
1. Data-Driven Decisions: Replace intuition with predictive analytics

2. Revenue Protection: Early detection of negative trends

3. Resource Optimization: Focus on high-impact improvements

4. Competitive Advantage: Better understanding of customer preferences

* For Product Teams
1. Recipe Improvement: Specific feedback on product issues

2. New Product Development: Insights into customer preferences

* For Marketing
1. Campaign Timing: Optimal periods for promotions

2. ROI Measurement: Quantify marketing impact on reviews

3. Customer Engagement: Strategic response to feedback


#### Add S3 bucket as DVC remote
!dvc remote add -d s3store s3://your-bucket-name/dvc-storage

#### Configure credentials (if not using IAM role)
!dvc remote modify s3store access_key_id YOUR_ACCESS_KEY
!dvc remote modify s3store secret_access_key YOUR_SECRET_KEY
!dvc remote modify s3store region us-east-1  # Your region





