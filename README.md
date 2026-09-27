
# 🧠 Next Word Prediction

An end-to-end Natural Language Processing project that predicts the **next word in a sequence of text** using a Long Short-Term Memory (LSTM) neural network.

The project covers the complete workflow from text preprocessing and tokenization to sequence generation, LSTM model training, model serialization, and deployment through an interactive **Streamlit web application**.

## 🚀 Project Overview

Next-word prediction is a fundamental NLP task used in applications such as:

* Predictive keyboards
* Autocomplete systems
* Text generation
* Conversational AI
* Writing assistance
* Language modeling

In this project, a collection of quotes is processed to create sequential training samples. An LSTM-based language model learns patterns in the text and predicts the most probable next word for a given input sequence.

The trained model is then integrated into a Streamlit application where users can enter text and receive a predicted next word.

## ✨ Features

* Text preprocessing and normalization
* Lowercase conversion
* Punctuation removal
* Tokenization using Keras Tokenizer
* Sequential training-data generation
* Pre-padding of input sequences
* Word-level next-word prediction
* LSTM-based language modeling
* Saved trained model for inference
* Saved tokenizer and sequence-length configuration
* Interactive Streamlit web interface
* Real-time next-word prediction

## 📊 Dataset

The project uses a quote dataset containing **3,038 records** with the following columns:

* `quote` — Text of the quote
* `Author` — Author of the quote

The dataset contains quotes from multiple authors including Albert Einstein, J.K. Rowling, Jane Austen, Marilyn Monroe, and others.

## 🔄 Machine Learning Pipeline

```text
Quote Dataset
     ↓
Text Cleaning
     ↓
Lowercase Conversion
     ↓
Punctuation Removal
     ↓
Tokenization
     ↓
Convert Text → Integer Sequences
     ↓
Create Input/Target Sequences
     ↓
Padding
     ↓
LSTM Model
     ↓
Next-Word Prediction
     ↓
Streamlit Deployment
```

## 🧹 Data Preprocessing

The quote text is first converted to lowercase and punctuation is removed.

The cleaned text is then tokenized using TensorFlow/Keras's `Tokenizer`.

Each quote is converted into a sequence of integer word IDs. For every sequence, progressively longer prefixes are used as inputs while the following word becomes the target.

For example:

```text
Input:  "the world"
Target: "is"

Input:  "the world is"
Target: "our"

Input:  "the world is our"
Target: "creation"
```

This converts the original text dataset into supervised learning samples for next-word prediction.

## 🧠 Model Architecture

The primary model uses the following architecture:

```text
Input Sequence
      ↓
Embedding Layer
      ↓
LSTM Layer
      ↓
Dense Layer
      ↓
Softmax
      ↓
Predicted Next Word
```

### Model Components

**Embedding Layer**

Converts integer word IDs into dense vector representations.

**LSTM Layer**

Learns sequential dependencies and contextual relationships between words.

**Dense Layer**

Produces a probability distribution across the vocabulary.

**Softmax Activation**

Selects the word with the highest predicted probability.

The project also contains an implementation of a `SimpleRNN` model for experimentation and comparison with the LSTM approach.

## 💾 Saved Model Files

The repository contains the files required to run inference without retraining the model:

| File            | Purpose                                           |
| --------------- | ------------------------------------------------- |
| `lstm_model.h5` | Trained LSTM model                                |
| `tokenizer.pkl` | Fitted text tokenizer                             |
| `max_len.pkl`   | Maximum sequence length used during preprocessing |

The Streamlit application loads these saved resources when it starts.

## 🖥️ Streamlit Application

The project includes an interactive Streamlit interface.

Users can:

1. Enter a sentence or partial sentence.
2. Click **Predict Next Word**.
3. Receive the model's predicted next word.

The application uses the tokenizer to convert the input into a numerical sequence, pads the sequence, passes it through the trained model, and selects the word corresponding to the highest predicted probability.

### Application Interface

```text
🧠 Next Word Prediction (LSTM)

Enter text:
[ Type a sentence here... ]

[ Predict Next Word ]

Predicted Next Word: ______
```

## 🛠️ Technologies Used

* **Python**
* **NumPy**
* **Pandas**
* **TensorFlow**
* **Keras**
* **LSTM**
* **SimpleRNN**
* **NLP**
* **Streamlit**
* **Pickle**
* **Jupyter Notebook / Google Colab**

## 📁 Project Structure

```text
next-word-prediction/
│
├── app.py                    # Streamlit application
├── codefile.ipynb            # Main NLP/LSTM implementation
├── RNNimplementation.ipynb   # Simple RNN implementation
├── qoute_dataset.csv         # Training dataset
├── lstm_model.h5             # Trained LSTM model
├── tokenizer.pkl             # Saved tokenizer
├── max_len.pkl               # Saved sequence length
├── requirements.txt          # Python dependencies
├── .gitignore                # Git ignored files
└── README.md                 # Project documentation
```

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/lstm-next-word-prediction.git
cd lstm-next-word-prediction
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser.

Enter a text sequence and click:

```text
Predict Next Word
```

## 🧪 Example

Example input:

```text
what are you
```

The trained model generates a predicted next word based on patterns learned from the training corpus.

## 🔬 RNN Experiment

The repository also contains `RNNimplementation.ipynb`, which demonstrates a separate SimpleRNN implementation.

The notebook uses a small set of positive and negative sentences and demonstrates:

* Tokenization
* Padding
* Embedding
* SimpleRNN
* Binary classification
* Model training
* Intermediate model construction
* Inspection of hidden states

This provides an additional practical demonstration of how recurrent neural networks process sequential text.

## 🎯 Learning Outcomes

Through this project, the following concepts were implemented:

* Natural Language Processing
* Text preprocessing
* Tokenization
* Sequence generation
* Word embeddings
* Recurrent Neural Networks
* LSTM networks
* Deep learning for NLP
* Model serialization
* Model inference
* Streamlit deployment

## 🔮 Future Improvements

Potential improvements include:

* Beam Search instead of simple `argmax` prediction
* Top-k next-word suggestions
* Better handling of out-of-vocabulary words
* Larger and more diverse training corpus
* Bidirectional architectures for related NLP tasks
* Transformer-based language models
* Improved text-generation controls
* Prediction confidence visualization
* Cloud deployment
* REST API for model inference

## 👩‍💻 Author

**Swastika Mukherjee**

B.Tech Data Science Student

---

⭐ If you find this project useful, consider giving the repository a star!
