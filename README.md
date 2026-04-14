# SMS Spam/Ham Classifier with NLP and Flask

## Project Overview
This project implements a machine learning model to classify SMS messages as either 'spam' or 'ham' (not spam) using Natural Language Processing (NLP) techniques. The trained model is then deployed as a simple web application using Flask, making it accessible via a public URL powered by ngrok.

## Features
-   **Data Loading and Preprocessing:** Downloads the SMS Spam Collection dataset, cleans text data (removes punctuation, converts to lowercase, tokenizes, removes stopwords, and lemmatizes).
-   **Feature Extraction:** Utilizes TF-IDF (Term Frequency-Inverse Document Frequency) to convert text messages into numerical feature vectors.
-   **Model Training:** Trains a Multinomial Naive Bayes classifier, a probabilistic machine learning model well-suited for text classification tasks.
-   **Model Evaluation:** Evaluates the model's performance using metrics such as accuracy, precision, recall, and F1-score.
-   **Model Persistence:** Saves the trained model and the TF-IDF vectorizer for future use without retraining.
-   **Flask Web Application:** A lightweight web interface built with Flask allows users to input a message and get an instant spam/ham prediction.
-   **Public Deployment (ngrok):** The Flask application is exposed to the internet using ngrok, providing a temporary public URL for easy access and demonstration.

## Technologies Used
-   **Python:** Programming language
-   **Pandas:** Data manipulation and analysis
-   **NLTK (Natural Language Toolkit):** Text preprocessing (stopwords, lemmatization)
-   **Scikit-learn:** Machine learning algorithms (TfidfVectorizer, MultinomialNB, model evaluation metrics)
-   **Flask:** Web framework for building the API and web interface
-   **Joblib:** For saving and loading Python objects (model, vectorizer)
-   **Requests & Zipfile:** For downloading and extracting the dataset
-   **Pyngrok:** For creating public URLs for the Flask app

## Getting Started

### Prerequisites
-   Python 3.x
-   Google Colab (recommended for easy setup and ngrok integration) or a local Python environment.
-   An `ngrok` authentication token (add it to Colab Secrets as `NGROK_AUTH_TOKEN` if using Colab).

### Installation
1.  **Clone the repository:**
    ```bash
    git clone <your-repo-link-here>
    cd sms-spam-ham-classifier
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas nltk scikit-learn Flask joblib pyngrok requests
    ```
3.  **Download NLTK data:**
    Ensure `stopwords` and `wordnet` are downloaded:
    ```python
    import nltk
    nltk.download('stopwords')
    nltk.download('wordnet')
    ```

### How to Run
1.  **Data Loading & Preprocessing:** Run the initial cells to download the dataset and preprocess the text messages.
2.  **Model Training:** Execute the cells to train the `Multinomial Naive Bayes` model and evaluate its performance.
3.  **Save Model Artifacts:** Run the cell to save the `tfidf_vectorizer.pkl` and `multinomial_nb_model.pkl` files.
4.  **Create `templates/index.html`:** Ensure the HTML template for the Flask app is created in a `templates` directory.
5.  **Start Flask App with ngrok:** Run the cell that starts the Flask application in a background thread and exposes it via ngrok. The public URL will be printed in the output.

## Usage
Once the Flask application is running and the ngrok URL is provided:
1.  Open the public URL in your web browser.
2.  You will see a simple interface where you can enter an SMS message.
3.  Click the "Predict" button to see if the message is classified as "Spam" or "Ham".

## Model Performance
-   **Accuracy:** [Your Model Accuracy, e.g., 0.9722]
-   **Precision:** [Your Model Precision, e.g., 0.9917]
-   **Recall:** [Your Model Recall, e.g., 0.7987]
-   **F1-Score:** [Your Model F1-Score, e.g., 0.8848]

## Live Demo
A live demo of the application can be accessed (while the Colab notebook is running) at: [Your ngrok public URL here, e.g., `https://remission-unfounded-demanding.ngrok-free.dev`]

## Contributing
Feel free to fork the repository, open issues, or submit pull requests.
