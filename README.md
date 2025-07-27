# Sequence Modeling in NLP: Hidden Markov Models and Viterbi Decoding
Built a Hidden Markov Model (HMM) from scratch for part-of-speech tagging using the Viterbi algorithm. Trained on the Brown Corpus (news, editorial, reviews) with the universal tagset. This project explores core NLP concepts through hands-on sequence modeling.

## Overview
This project implements a Hidden Markov Model (HMM) combined with the Viterbi algorithm to perform part-of-speech (POS) tagging on English text. Using the Brown Corpus (categories: news, editorial, reviews) with the universal POS tagset, I built and evaluated multiple HMM variants to understand their effectiveness in sequence tagging tasks.

## Data
- Brown Corpus from the NLTK library
- Focused on news, editorial, and reviews categories
- Tags based on the simplified universal tagset, which includes categories such as NOUN, VERB, ADJ, ADV, PRON, DET, and others

## Methodology
1. Data Preparation
   - Loaded the Brown Corpus with specified categories and universal tags
   - Preprocessed data by lowercasing all words to reduce vocabulary size
   - Split the dataset into training and testing sets

2. Vocabulary Construction
   - Extracted unique words and tags from the training set to build dictionaries
   - Avoided using test data during dictionary creation to prevent data leakage

3. Model Training
   - Utilized NLTK’s HiddenMarkovModelTrainer to train five HMM variants:
     - Basic HMM without smoothing
     - HMM with Lidstone smoothing (gamma = 0.01)
     - HMM with Lidstone smoothing (gamma = 0.1)
     - HMM using Maximum Likelihood Estimation (MLE)
     - HMM using Expected Likelihood Estimation (ELE)

4. Tag Prediction
   - Used the Viterbi algorithm (best_path() method) to predict POS tags on test sentences

5. Evaluation
   - Measured Precision, Recall, and F1-score using printConlleval
   - Analyzed error patterns with confusion matrices (printConfusionMatrix)
   - Compared model performances and discussed smoothing effects

6. Model Export
   - Selected the best-performing model (Lidstone smoothing, gamma=0.01)
   - Serialized and saved the model using dill for future use

## Results & Insights
- Lidstone smoothing with gamma = 0.01 provided the best balance of accuracy and generalization
- Minimal performance difference observed between Lidstone smoothing gamma values 0.01 and 0.1
- Models without smoothing showed significantly lower accuracy
- The MLE-based model performed similarly to the ‘pure’ unsmoothed HMM
- Smoothing techniques notably improved tagging for rare or ambiguous tags (e.g., ‘X’ category)








