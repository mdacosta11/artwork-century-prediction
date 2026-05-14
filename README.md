## Project Overview
This project uses machine learning to predict the century in which an artwork was created using museum metadata from the Art Institute of Chicago API.

The metadata includes fields such as:
- title
- artist
- date information
- medium
- dimensions
- classification
- department

The goal is to test whether artwork metadata alone contains enough information to classify an artwork by century.

## Problem Statement
Museums and digital archives contain large collections of artworks, but not every piece has complete or easily usable date information. Predicting the century of creation can help with cataloging, archiving, historical analysis, and organizing digital museum collections more efficiently.

## Data Source
This project uses the public API from the Art Institute of Chicago:

- Art Institute of Chicago API

## Workflow
The notebook follows these main steps:

1. Collect artwork metadata from the Art Institute of Chicago API
2. Clean the data and extract usable year information
3. Convert years into century labels
4. Build text representations from artwork metadata
5. Train machine learning models using two approaches:
   - TF-IDF features
   - Doc2Vec embeddings
6. Compare model performance
7. Visualize embedding behavior using t-SNE

## Models Used
### TF-IDF Approach
- Logistic Regression
- k-NN
- Random Forest

### Doc2Vec Approach
- Logistic Regression
- k-NN
- Random Forest

## Main Results
The TF-IDF models performed better than the Doc2Vec models on this dataset.

Best result:
- Random Forest with TF-IDF: 0.768 accuracy

Example comparison:

| Model | Accuracy |
|------|----------|
| Random Forest | 0.768 |
| k-NN | 0.756 |
| Logistic Regression | 0.743 |
| k-NN (Doc2Vec) | 0.503 |
| Random Forest (Doc2Vec) | 0.484 |
| Logistic Regression (Doc2Vec) | 0.276 |

## Key Findings
- Artwork metadata can be used to predict century with reasonable accuracy.
- TF-IDF worked better than Doc2Vec for this task.
- Exact metadata words were more useful than dense document embeddings.
- The Doc2Vec t-SNE visualization showed strong overlap between centuries, suggesting that the metadata is not cleanly separable by time period.

## Limitations
- Different centuries often share similar metadata patterns.
- Some classes may be imbalanced.
- Metadata text is short and structured, which may limit embedding quality.
- The project uses one museum data source.

## How to Run
1. Open the notebook in Google Colab or Jupyter.
2. Install the required packages.
3. Run the cells in order.

## Files
- `Artwork_Century_Prediction.ipynb` — main notebook
- `requirements.txt` — required Python packages

## Authors
Anisa Hyder
Emilio Altamira
Michael Acosta
