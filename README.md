# **LSTM Quote Generator**

A **deep learning project** that generates text one word at a time using an **LSTM-based language model** trained on a collection of quotes.

## **Project Overview**

This project demonstrates a **next-word prediction and text generation pipeline** using **TensorFlow/Keras**.

The notebook:
- Loads the quote dataset from `qoute_dataset.csv`
- Converts text to lowercase and removes punctuation
- Tokenizes the quotes
- Creates input/output word sequences
- Pads input sequences
- Uses an **Embedding Layer** and **LSTM Model**
- Predicts the next word from seed text
- Generates multiple words sequentially
- Saves the model and preprocessing objects

## **Technologies Used**

- **Python**
- **NumPy**
- **Pandas**
- **Seaborn**
- **Matplotlib**
- **TensorFlow / Keras**
- **LSTM**
- **Embedding Layer**

## **Saved Files**

- `qoute_dataset.csv` — Quote dataset
- `lstm_model.h5` — Saved LSTM model
- `tokenizer.pkl` — Saved tokenizer
- `max_len.pkl` — Saved maximum sequence length

## **Project Structure**

```text
LSTM-Quote-Generator/
├── codefile.ipynb
├── qoute_dataset.csv
├── lstm_model.h5
├── tokenizer.pkl
├── max_len.pkl
├── app.py
├── screenshot.png
└── README.md
```

## **Model Architecture**

| Layer | Configuration |
|---|---|
| **Embedding** | Vocabulary: 10,000, Dimension: 50 |
| **LSTM** | 128 units |
| **Dense** | 10,000 units |
| **Activation** | Softmax |
| **Optimizer** | Adam |
| **Loss** | Categorical Crossentropy |
| **Metric** | Accuracy |

## **Data Preprocessing**

**Quotes → Lowercase → Remove Punctuation → Tokenization → Integer Sequences → Input/Target Pairs → Padding → One-Hot Encoding**

Example:

**Input:** `I love machine`  
**Target:** `learning`

## **Text Generation**

The model predicts **one word at a time** from a seed sentence. Each predicted word is added to the text and used to predict the next word.

```python
seed = "are you a "
generate_text(lstm_model, tokinizer, seed, max_len, 10)
```

## **Streamlit Web App**

This project includes a **Streamlit-based web application** that provides an interactive interface for generating text using the trained LSTM model.

### **How to Run the App**

First, navigate to the project directory:

```bash
cd LSTM-Quote-Generator
```

Install Streamlit if required:

```bash
pip install streamlit
```

Run the application:

```bash
streamlit run app.py
```

The application will open in your browser.

You can also access it at:

```text
http://localhost:8501
```

### **App Preview**

![LSTM Quote Generator App](screenshot.png)
