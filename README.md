# Astra Capstone: Product Substitutability Analysis

## Overview

This project analyzes product substitutability in retail scanner data using a combination of attribute similarity and transaction co-occurrence metrics. It provides a reproducible pipeline for generating substitutability scores, optimizing classification thresholds, and evaluating performance across multiple stores.

## Folder Structure

- **Training/**  
  Contains main analysis notebooks, summary CSVs, and threshold optimization results.
  - `Cat_Compat_Clean.ipynb`: Main notebook for threshold optimization, categorization, and evaluation.
  - `substitutability_optimization_summary.csv`: Store-level threshold optimization summary.
  - `confusion_matrix_summary_threshold_079.csv`: Confusion matrix summary for S001-S010.
  - `complete_confusion_matrix_summary_threshold_079.csv`: Combined summary for S001-S015.

- **NewCode/**  
  Contains modular notebooks for generating and merging scores.
  - `Attribute.ipynb`: Computes attribute-based similarity scores for product pairs.
  - `Transaction.ipynb`: Computes transaction-based substitutability scores using lift, Yule's Q, and correlation.
  - `Merge.ipynb`: Merges attribute and transaction scores into final substitution scores.
  - `Stores.ipynb`: Store-level processing and categorization.

- **NewData/**  
  Contains all generated datasets and store-level results.
  - `attribute_scores.csv`: Attribute similarity scores for product pairs.
  - `transaction_scores.csv`: Transaction-based substitutability scores.
  - `final_substitution_scores.csv`: Merged scores for all product pairs.
  - `StoresLevel/`: Categorized and raw scores for each store (S001-S015).

- **OldCode/**  
  Contains legacy notebooks for reference.

- **OldData/**  
  Contains original raw datasets and store-level files.

## Key Concepts

- **Attribute Score**: Measures similarity between products based on their attributes.
- **Transaction Score**: Measures substitutability using co-occurrence metrics (lift, Yule's Q, correlation).
- **Weighted F1 Score**: Custom F-beta score with recall/precision weights for optimal threshold selection.
- **Threshold Optimization**: Finds the best cutoff for classifying substitutability per store.
- **Categorization**: Assigns 'Yes'/'No' substitutability labels to product pairs based on optimized thresholds.
- **Evaluation**: Confusion matrix and summary statistics for each store and overall.

## How to Use

1. **Generate Scores**  
   - Run `Attribute.ipynb` and `Transaction.ipynb` in `NewCode/` to create `attribute_scores.csv` and `transaction_scores.csv`.

2. **Merge Scores**  
   - Run `Merge.ipynb` to combine attribute and transaction scores into `final_substitution_scores.csv`.

3. **Store-Level Analysis**  
   - Run `Stores.ipynb` to process each store and categorize product pairs.

4. **Threshold Optimization & Evaluation**  
   - Use `Cat_Compat_Clean.ipynb` in `Training/` for threshold optimization, categorization, and performance evaluation.
   - Results are saved in summary CSVs for further analysis.

## Data Sources

- **products.csv**: Product metadata.
- **sales_transactions.csv**: Transaction records.
- **edade.xlsx**: Ground truth for product substitutability.
- **StoresLevel/**: Store-level product pair scores.

## Outputs

- Categorized product pairs for each store.
- Optimized thresholds and performance metrics.
- Confusion matrix summaries for individual and combined stores.

## Requirements

- Python 3.x
- pandas, numpy, scikit-learn, matplotlib, seaborn

## Reproducibility

All notebooks are modular and can be run independently. Outputs are saved as CSVs for downstream analysis.

