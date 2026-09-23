LSTM Quote Generator

A deep learning project that generates text one word at a time using an LSTM-based language model trained on a collection of quotes.

Project Overview

This project demonstrates a basic next-word prediction and text generation pipeline using TensorFlow/Keras.

The notebook:

Loads a quote dataset from qoute_dataset.csv

Converts quotes to lowercase

Removes punctuation

Tokenizes the text

Converts quotes into input/output word sequences

Pads input sequences to a common length

Uses an embedding layer to represent words

Builds an LSTM language model

Predicts the next word from a given seed text

Generates multiple words sequentially from a seed sentence

Saves the trained model and preprocessing objects for later use

Technologies Used

Python

NumPy

Pandas

Seaborn

Matplotlib

TensorFlow / Keras

LSTM (Long Short-Term Memory)

Embedding Layer

Model Architecture

The LSTM model used in the notebook contains:

Embedding Layer

Vocabulary size: 10,000

Embedding dimension: 50

LSTM Layer

Number of units: 128

Dense Output Layer

Number of units: 10,000

Activation: softmax

The model is compiled with:

Optimizer: Adam

Loss: categorical_crossentropy

Metric: accuracy

Data Preprocessing

The quote text is preprocessed before training:

Raw quotes
    ↓
Convert to lowercase
    ↓
Remove punctuation
    ↓
Tokenization
    ↓
Convert words to integer sequences
    ↓
Create input/target word pairs
    ↓
Pad input sequences
    ↓
One-hot encode target words

For each quote, progressively longer sequences are created. For example:

"I love machine learning"

can produce training pairs conceptually like:

"I"                       → "love"
"I love"                  → "machine"
"I love machine"          → "learning"

Text Generation

The notebook uses a seed sentence and predicts one word at a time.

Example:

seed = "are you a "
generate_text(lstm_model, tokinizer, seed, max_len, 10)

The predicted word is appended to the seed text, and the updated text is used to predict the next word. This process continues for the requested number of words.

Saved Files

The project uses/saves the following files:

qoute_dataset.csv — quote dataset used by the notebook

lstm_model.h5 — saved trained LSTM model

tokenizer.pkl — saved Keras tokenizer

max_len.pkl — saved maximum input sequence length

These files allow the trained model and preprocessing configuration to be reused without rebuilding them from scratch.

How to Run

1. Install dependencies

pip install numpy pandas seaborn matplotlib tensorflow

2. Keep the required files in the project directory

Make sure the following files are available:

qoute_dataset.csv
lstm_model.h5
tokenizer.pkl
max_len.pkl

3. Open the notebook

Open:

codefile.ipynb

in Jupyter Notebook or VS Code.

4. Run the notebook

Run the cells in order.

Making a Prediction

The notebook defines a predictor() function that takes:

predictor(model, tokenizer, text, max_len)

It converts the input text into a sequence, pads it, passes it to the LSTM model, and returns the predicted next word.

Project Structure

LSTM-Quote-Generator/
│
├── codefile.ipynb
├── qoute_dataset.csv
├── lstm_model.h5
├── tokenizer.pkl
├── max_len.pkl
└── README.md



Learning Outcomes

This project provides practical exposure to:

Natural Language Processing (NLP)

Text preprocessing

Tokenization

Sequence generation

Word embeddings

Recurrent Neural Networks (RNNs)

LSTM networks

Next-word prediction

Text generation

Saving and loading Keras models

Saving preprocessing objects with Python pickle