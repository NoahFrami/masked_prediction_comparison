Masked Language Modeling Comparison
Name: Noah C Frami  
Date: 10/28/2026  
Course: Natural Language Processing (NLP)
Project Overview
This project compares two approaches to predicting missing words in a sentence:
Manual Context Model: A simple model built from words in a text corpus. It uses nearby words to find possible predictions.
BERT: A pretrained language model (`bert-base-uncased`) that predicts masked words using context from both sides of the missing word.
The goal is to see how the two models compare and how the size and contents of the corpus affect the manual model.
How It Works
The program:
Loads text from `corpus.txt`.
Converts the text to lowercase, removes punctuation, and splits it into tokens.
Builds a manual context model using a window size of 2.
Loads the pretrained BERT fill-mask pipeline.
Tests three example sentences:
`The cat sat on the [mask]`
`I went to the [mask] to buy food`
`She deposited money in the [mask]`
Prints the predictions from both models so they can be compared.
The manual model counts words that appeared with matching context in the corpus. BERT uses a pretrained model and returns its top predictions with scores.
Requirements
Python 3.10 or newer recommended
PyTorch
Transformers
Internet connection for the initial BERT model download
Project Files
Your project folder should contain:
```text
your-project-folder/
├── masked_language_modeling_comparison.py
└── corpus.txt
```
Use your actual Python filename if it is different.
Setup and Run (PyCharm)
Open the project in PyCharm.
Make sure `corpus.txt` is in the project's working directory (usually the main project folder).
Open the PyCharm terminal.
Install the required packages:
```bash
   python -m pip install torch transformers
   ```
Run the Python file from PyCharm.
The first run may take longer because BERT needs to download its model files.
Modifying the Corpus
Edit `corpus.txt` and add or change sentences. Run the program again and compare the manual model's predictions.
The manual model can only predict words supported by contexts found in its corpus. A small or limited corpus may lead to missing or unhelpful predictions.
What to Evaluate
For the assignment, record observations about:
Which model gives more useful predictions.
How changing `corpus.txt` changes the manual model's results.
At least one failure case for the manual model.
At least one example where BERT is also imperfect.
BERT is pretrained, so changing `corpus.txt` affects the manual model, but does not retrain BERT.
Limitations
The manual model relies on exact context matches, so it may return no predictions for unseen contexts.
The manual model uses word counts rather than deeper language understanding.
The manual prediction function expects `[mask]` as a separate word and does not normalize punctuation the same way the corpus preprocessing does.
BERT can suggest plausible words that do not fit the intended meaning. Its prediction scores are not guarantees of correctness.
This program prints comparison prompts, but the model results and your actual observations still need to be reviewed.
Conclusion
This project demonstrates the difference between a basic corpus-based context model and a pretrained transformer model. Comparing their predictions helps show how corpus coverage and broader context can affect masked word prediction.
