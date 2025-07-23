#  Wallet Behavior Scoring with Machine Learning

##  Overview  
This project builds a machine learning model to evaluate and score cryptocurrency wallets based solely on their historical transaction behavior. Each wallet is assigned a credit-like score ranging from 0 to 1000 — higher scores indicate responsible, reliable activity, while lower scores reflect risky, bot-like, or exploitative behavior.

##  Objective  
To uncover behavior patterns that signal trustworthiness or risk in wallet activity by analyzing only their transaction history.

##  Data  
The dataset includes over 100,000 DeFi transaction records in JSON format. Each transaction contains:  
- Wallet address  
- Transaction type (e.g., deposit, borrow, repay)  
- Timestamps  
- Amounts  
- Asset prices  

No personal identifiers or labels were used — only behavioral data.

##  Feature Engineering  
For each wallet, the following features were computed:  
- Total number of transactions  
- Frequency of transaction types (deposit, borrow, repay, liquidation)  
- Ratios (borrow-to-deposit, repay-to-borrow)  
- Active lifespan (duration between first and last transaction)  
- Average transaction value in USD  

These were aggregated into one row per wallet and used as input to the model.

##  Modeling  
A Gradient Boosting Regressor (XGBoost) was used to score wallets between 0 and 1000.  

Why XGBoost?  
- Works well with tabular data  
- Handles feature importance analysis  
- Good at dealing with outliers and skew  

The model output was normalized using min-max scaling, then scaled to the 0–1000 range.

##  Output  
The final output is a CSV file containing:  
- Wallet address  
- All engineered features  
- Score (0–1000)  

File: wallet_scores.csv

##  Analysis  
See analysis.md for:  
- Score distribution graph (0–100, 100–200, ..., 900–1000)  
- Patterns observed in low vs high scoring wallets  
- Visual interpretation and conclusions  

Example insights:  
- Wallets under 200 often had high borrow-to-deposit ratios and short usage lifespans.  
- Wallets above 800 were consistent, repaid debts quickly, and stayed active longer.

##  Usage  
You can use this scoring approach for:  
- Risk classification in DeFi protocols  
- User segmentation  
- Bot detection  

It’s a general framework you can adapt for live monitoring, more features, or integrating protocol-specific behaviors.

##  Folder Structure  
- wallet_scores.csv – Final results  
- generate_features.py – Code to process transactions and extract features  
- train_model.ipynb – Google Colab notebook with training and scoring logic  
- analysis.md – Wallet scoring behavior report with visualizations  
- README.md – Project summary and guide (this file)

##  How to Run  
1. Upload your JSON file to Google Colab  
2. Use the feature generation code to produce features  
3. Train the model and assign scores  
4. Download output and push everything to GitHub

##  Contributor  
Dheeraj S
