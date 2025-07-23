# • Wallet Score Analysis Report

## • Introduction  
This file contains a detailed analysis of the credit-like scores assigned to wallets based on their transaction history. The model outputs scores ranging from 0 to 1000. This analysis aims to understand patterns in wallet behavior and evaluate the reliability of score-based segmentation.

## • Score Distribution  
The score range was divided into 10 buckets for visualization and interpretation:  
• 0–100  
• 100–200  
• 200–300  
• 300–400  
• 400–500  
• 500–600  
• 600–700  
• 700–800  
• 800–900  
• 900–1000  

<img width="984" height="583" alt="Histogram of wallet scores" src="https://github.com/user-attachments/assets/2ea53ca0-d129-44b9-85f7-1e8371612330" />


Observations:  
• The majority of wallets scored between 300 and 600.  
• Very few wallets scored below 200 or above 900, indicating rare extreme behaviors.  
• Distribution is slightly skewed towards the middle ranges.

## • Low-Scoring Wallet Behavior (0–300)  
Wallets in this category often displayed patterns that indicate risk, irregularity, or possible bot-like behavior:  
• High borrow-to-deposit ratios  
• Frequent liquidations  
• Very short activity duration (e.g., only active for 1–2 days)  
• Very high transaction frequency in short periods  
• Low or zero repayments

These wallets might be bots, test accounts, or exploitative users in DeFi environments.

## • Mid-Range Wallets (400–700)  
These wallets exhibited balanced behavior:  
• Moderate activity across borrow, deposit, and repay  
• Minimal or no liquidation activity  
• Regular usage patterns over weeks  
• Reasonable ratios and healthy asset movement

This is the “average user” cluster — not risky, not highly reliable either.

## • High-Scoring Wallet Behavior (800–1000)  
These wallets show behavior typical of reliable, healthy DeFi participants:  
• Regular deposits and timely repayments  
• Little to no liquidations  
• Active for longer durations  
• Consistent transaction behavior and steady asset growth  
• Balanced ratios between all types of transactions

They represent the “trusted” wallets that most protocols would likely prioritize or whitelist.

## • Conclusion  
The score-based segmentation shows meaningful differences between wallets, purely based on behavior. These scores can be integrated into automated systems for DeFi protocol risk assessment, access control, user segmentation, and fraud detection.

Future improvements:  
• Add protocol-specific behavior features  
• Include time-weighted metrics (recent behavior matters more)  
• Incorporate external reputation or KYC signals for supervised fine-tuning
