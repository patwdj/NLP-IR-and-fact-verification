# NLP-IR-and-fact-verification
Natural Language Processing (NLP) project: An automated fact checking system for climate science claims. Involves Information Retrieval (IR) using TF-IDF and BM-25, and Classification using BERT and RoBERTa.

Notes:
- If at any point kernel crashes but a pickling point have been passed, processing up to the last pickling point can be skipped and data loaded directly instead. A sample of how to load pre-processed data and scores is available at the bottom of the notebook under "Load Preprocessed Data and Scores". Adjust files and variable names to as required.
- Action points will require action from the user i.e. updating variables based on the model to be tested. These are noted in comments and markdowns.

## Methodology Diagram
<img width="284" alt="Screen Shot 2023-07-13 at 23 27 39" src="https://github.com/patwdj/nlp-IR-and-fact-verification/assets/80323885/9510d189-fd2e-4aa5-82a0-e13c88dcf016">

## Research Questions and Final Performance
- Research Questions:
  - [RQ1] To what extent can BM-25, TF-IDF, and word2vec be used to gather relevant evidences?
  - [RQ2] Can transformer models BERT and RoBERTa be used to predict claim labels?
  - [RQ3] Given the predictions, what is the best approach to selecting the final list of evidences?
- Final Performance:
  - Dev: 0.1519 F-SCORE, 0.5519 A-SCORE (Accuracy), and 0.2382 H-SCORE (Harmonic mean of F and A)
  - Test: 0.0896 F-SCORE, 0.5584 A-SCORE (Accuracy), and 0.1544 H-SCORE (Harmonic mean of F and A)

## Data Required
Data provided as part of assigment has not been uploaded to this repository:
- [train-claims,dev-claims].json: JSON files for the labelled training and development set;
- [test-claims-unlabelled].json: JSON file for the unlabelled test set;
- evidence.json: JSON file containing a large number of evidence passages (i.e. the “knowledge source”);
- dev-claims-baseline.json: JSON file containing predictions of a baseline system on the development set;
- eval.py: Python script to evaluate system performance (see “Evaluation” below for more details).

Format of data:
- Labelled claim files has the following format:
```
{
  "claim-2967":
  {
    claim_text: "[South Australia] has the most expensive electricity in the world."
    claim_label: "SUPPORTS"
    evidences: ["evidence-67732", "evidence-572512"]
  },
  "claim-375":
  ...
}
```
- The list of evidence IDs (e.g. evidence-67732, evidence-572512) are drawn from the evidence passages in evidence.json:
```
{
  "evidence-0": "John Bennet Lawes, English entrepreneur and agricultural scientist",
  "evidence-1": "Lindberg began his professional career at the age of 16, eventually ...",
  ...
}
```


## Directory Structure Required
```
|- final.ipynb
|- project-data
	|- dev-claims.json
	|- evidence.json
	|- test-claims-unlabelled.json
	|- train-claims.json
|- json
	|- eval.py
	|- dev-claims-baseline.json
|- pickles
	|- 
|- csv
	|-
```

#
***Completed in June 2023***

