# Predicting the Century of Creation of an Artwork Using Museum Metadata

## Project Overview
This project uses machine learning to predict the century in which an artwork was created using museum metadata from two public museum collections: the Art Institute of Chicago and The Metropolitan Museum of Art.

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
Museums and digital archives contain large collections of artworks, but not every artwork has complete, consistent, or easy-to-use date information. This creates challenges for cataloging, organizing collections, and supporting historical research. Our project focuses on predicting the century in which an artwork was created using museum metadata, such as the title, artist, medium, dimensions, classification, and department. The goal is to see whether these metadata fields contain enough historical signal to help identify the artwork’s time period. This problem is important because a model that can estimate an artwork’s century could help museums improve digital archiving, make large collections easier to manage, and support art historians when studying patterns and trends across time.

## Data Sources
This project uses public API data from:

- Art Institute of Chicago API
- The Metropolitan Museum of Art Collection API

## Workflow
The notebook follows these main steps:

1. Collect artwork metadata from the Art Institute of Chicago API and The Metropolitan Museum of Art API
2. Combine and clean the data
3. Extract usable year information
4. Convert years into century labels
5. Build text representations from artwork metadata
6. Train machine learning models using two approaches:
   - TF-IDF features
   - Doc2Vec embeddings
7. Compare model performance
8. Visualize embedding behavior using t-SNE

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
- Results can depend on the quality and consistency of museum metadata.

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
