# ML-Intern-Quantacus-Hiring 


# Email Marketing Campaign Optimization - Documentation

## Overview

This project analyzes an email marketing campaign for an e-commerce site and builds a machine learning model to optimize future campaigns by predicting which users are most likely to click links within marketing emails.

## Data Description

### Input Data

1. **email_table.csv**
   - `email_id`: Unique identifier for each email
   - `email_text`: Email content length ("long text" or "short text")
   - `email_version`: Personalization ("personalized" or "generic")
   - `hour`: Local time when email was sent (0-23)
   - `weekday`: Day of week when email was sent
   - `user_country`: User's country based on IP address
   - `user_past_purchases`: Number of items previously purchased by user

2. **email_opened_table.csv**
   - `email_id`: IDs of emails that were opened

3. **link_clicked_table.csv**
   - `email_id`: IDs of emails where links were clicked

### Processed Data Features

- Original features (encoded):
  - Email text length
  - Email version
  - User country
  - Weekday
- Engineered features:
  - Cyclical time features (sine/cosine of hour)
  - Binned purchase history
- Target variable:
  - `clicked`: Binary indicator (1 if link clicked, 0 otherwise)

## Analysis Approach

### Key Metrics Calculated

1. **Email Open Rate**: Percentage of users who opened the email
2. **Click-Through Rate (CTR)**: Percentage of users who clicked the link
3. **Click-to-Open Rate**: Percentage of opened emails that resulted in clicks

### Machine Learning Model

**Algorithm**: Random Forest Classifier

**Why Random Forest?**
- Handles both numerical and categorical features well
- Captures non-linear relationships
- Provides feature importance for interpretation
- Robust to overfitting

**Model Performance Metrics:**
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC


## Key Findings

### Campaign Performance

| Metric               | Value   |
|----------------------|---------|
| Email Open Rate      | 10.35%  |
| Click-Through Rate   | 2.12%  |
| Click-to-Open Rate   | 20.48%  |

### Segmentation Insights
![image](https://github.com/user-attachments/assets/69376436-48c0-43b8-9c95-66dc4561eaf0)


1. **Email Content**:
   - Short text emails performed XX% better than long text
   - Personalized emails showed XX% higher CTR

2. **Timing**:
   - Best performing day: [Weekday]
   - Optimal sending time: [XX:00 - XX:00]

3. **User Characteristics**:
   - Top responding country: [Country]
   - Most engaged user segment: [X-X past purchases]


## Recommendations

1. **Targeting Strategy**:
   - Focus on users with [specific characteristics]
   - Prioritize [country] for future campaigns
   - Target users with [X-X] past purchases

2. **Content Optimization**:
   - Use short text versions
   - Personalize emails when possible

3. **Timing Optimization**:
   - Send emails on [optimal weekday]
   - Preferred sending window: [XX:00 - XX:00]

4. **Testing Framework**:
   - Implement A/B testing for continuous improvement
   - Use multi-armed bandit approach for content variants

## Future Work

1. Incorporate additional user behavior data
2. Implement real-time scoring system
3. Develop reinforcement learning for dynamic optimization
4. Add natural language processing for subject line optimization

## Dependencies

- Python 3.8+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- jupyter

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
