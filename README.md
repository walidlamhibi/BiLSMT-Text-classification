# Text Classification with BiLSTM

This project implements a **BiLSTM (Bidirectional Long Short-Term Memory)** model for the automatic classification of text into four categories:

- **World**
- **Sports**
- **Business**
- **Sci/Tech**

## Objective
The primary goal is to build a performant model to categorize news articles based on their textual content.

## Dataset
The dataset used is [AG News Classification](https://www.kaggle.com/datasets/amananandrai/ag-news-classification-dataset).

### Dataset Features:
- **120,000 articles for training.**
- **7,600 articles for testing.**
- Each article contains:
  - `Title`: The article's title.
  - `Description`: A summary of the article.
  - `Class Index`: The category (0: World, 1: Sports, 2: Business, 3: Sci/Tech).

## Methodology
1. **Data Preprocessing**:
   - Combine the `Title` and `Description` columns to enrich the text.
   - Clean the data (remove special characters, convert to lowercase).
   - Convert text to numerical sequences using a **Tokenizer**.
   - Normalize sequences with padding (max length: 300).

2. **BiLSTM Model Construction**:
   - **Embedding Layer**: Word vector representations.
   - **Bidirectional LSTM**: Captures contextual relationships in both directions.
   - **Dense Layers**: Extract complex relations.
   - **Output Layer**: Predicts the 4 classes via Softmax.

3. **Training and Validation**:
   - Optimizer: **Adam**.
   - Loss function: **Categorical Crossentropy**.
   - Trained for 15 epochs with a batch size of 64.

4. **Deployment with a User Interface**:
   - Used **Streamlit** to allow users to test the model with custom texts.

## Results
- **Training Accuracy**: ~95%
- **Validation/Test Accuracy**: ~80-85%

## Usage
1. Enter a text in the Streamlit user interface.
2. Click the button to predict the category.
3. View the predicted class and associated probabilities.

## Project Structure
```
|-- app.py                 # Streamlit application script
|-- model.h5               # Saved BiLSTM model
|-- tokenizer.pkl          # Saved tokenizer
|-- requirements.txt       # List of dependencies
|-- README.md              # Project documentation
```

## Author
**LAMHIBI .W**
