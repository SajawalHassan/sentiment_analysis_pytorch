# Sentiment Analysis LSTM README

## Overview
This project focuses on building a sentiment analysis model using a Long Short-Term Memory (LSTM) network. The purpose of this model is to analyze text data, specifically reviews, and classify them according to their sentiment (positive or negative). The model has been developed in Python using PyTorch, Pandas, Matplotlib, NLTK, and Numpy.

## Tokenization Method
The text data is preprocessed and tokenized with the following method:

1. **Stopwords Removal**: Commonly used words such as 'is', 'are', 'am' are removed from the reviews as they usually don't contribute to sentiment.
2. **Top 1000 Words**: The 1000 most common words in the reviews are identified.
3. **Numerical Assignment**: These 1000 words are assigned a unique numerical value based on their popularity.
4. **Review Reconstruction**: Each review in the training set (`X_train`) is reconstructed using only these 1000 common words.

## LSTM Model Structure
The LSTM model is built using PyTorch and has the following structure:

- **Hidden Dimensions (`hidden_dim`)**: Size of the hidden layers in the LSTM.
- **Number of Layers (`no_layers`)**: Number of layers in the LSTM.
- **Embedding (`emb`)**: An embedding layer that converts the input numerical tokens into embeddings of a specified size.
- **LSTM Layer (`lstm`)**: The LSTM layer with parameters - `input_size` set to the embedding dimension, `hidden_size` to `hidden_dim`, `num_layers` to `no_layers`, and `batch_first` set to `True`.
- **Dropout (`dropout`)**: A dropout layer with a dropout rate of 0.3 to prevent overfitting.
- **Fully Connected Layer (`fc`)**: A linear layer that maps the output of the LSTM to the desired output size.
- **Sigmoid Activation (`sig`)**: A sigmoid activation function to obtain the final output in the range of 0 to 1, indicative of sentiment.

## Dependencies
Ensure you have the following Python libraries installed:
- Python (3.x)
- PyTorch
- Pandas
- Matplotlib
- NLTK
- Numpy

You can install these packages using pip:
```bash
pip install torch pandas matplotlib nltk numpy
```

## Contributing
Contributions to this project are welcome. Please ensure that you follow the existing code structure and comment your code adequately. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)

Please note that this project is for educational purposes and might require further modifications for production use.
