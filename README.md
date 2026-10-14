# econ3916-lab06-sampling
# Sampling for Machine Learning — Train-Test Splits

## Objective

In this lab I looked at how the way a sample is drawn, from a train test split to a national poll, changes how much I can trust the results.

## Methodology

- I explored the Titanic dataset, which has 891 passengers with survival as the target.
- I compared a naive train test split with a stratified one and checked that stratifying keeps the survival rate the same in both halves.
- I found data leakage in a StandardScaler step and a SimpleImputer step, then fixed both by splitting first, fitting only on the training rows, and only transforming the test rows.
- I wrote a function called split_by_share that splits a table by a test share and a seed, and I checked it against the lab's own split.
- I simulated the 1936 Literary Digest polling failure on 10 million voters.
- I computed Meng's data defect correlation and compared a biased sample of [YOUR VALUE] responses with a random sample of 50,000.
- I ran 100 replications comparing the biased sample and the random sample.

## Key Findings

- Stratifying the split kept the survival rate the same in the training and test halves, while the naive split only got close by chance.
- Fitting a scaler or imputer before splitting lets information from the test rows leak into training, so the right order is to split first and fit on the training rows only.
- Sample design beats sample size. The biased sample of [YOUR VALUE] responses was less accurate than the random sample of 50,000.
- A data defect correlation of [YOUR VALUE] produced an error of [YOUR VALUE] percentage points.
