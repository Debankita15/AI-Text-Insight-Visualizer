# AI-Enhanced Interactive Textual Insights and Visualization Platform

## Overview

This is a **work-in-progress** project, part of my **volunteer work**, aimed at building an interactive platform for analyzing and visualizing textual data using AI. The platform allows users to upload text files (TXT/CSV) and get AI-driven insights such as text summarization, sentiment analysis, and theme extraction. The app also provides visualizations like sentiment distribution, word clouds, and thematic relationship networks.

The app is hosted using **ngrok** on **Google Colab**, leveraging **Streamlit** for the web interface and **SQLite** for data storage.

---

## Features

- **Text Upload**: Upload `.txt` or `.csv` files to analyze the text content.
- **Pretraied LLM used**: Utilizes **Hugging Face Transformers** for text summarization and sentiment analysis, which are built on pre-trained LLMs.
  - **Summarization**: The model **sshleifer/distilbart-cnn-12-6** from Hugging Face is a variant of BART (Bidirectional and Auto-Regressive Transformers), which is an LLM designed for natural language generation tasks like summarization.
  - **Sentiment Analysis**: The model d**istilbert-base-uncased-finetuned-sst-2-english** from Hugging Face is a version of BERT (Bidirectional Encoder Representations from Transformers) used for sentiment analysis, which is also a pre-trained LLM fine-tuned for specific tasks.
- **Theme Extraction**: Extract keywords and themes from the text using **YAKE** and **Gensim LDA topic modeling**.
- **Visualization**:
  - Sentiment Distribution Pie Chart.
  - Word Cloud for extracted themes.
  - Thematic Relationship Network using **Plotly** and **NetworkX**.
- **Interactive Q&A**: Ask questions related to the uploaded texts (feature is currently under development).
- **Fun Task**: A number guessing game is included to keep users engaged while data is being processed.

---

## Weekly Update

### Week 1: September 9, 2024 - September 15, 2024
- **Initial Planning and Setup**:
  - Defined the project scope and features.
  - Set up the project environment on Google Colab.
  - Installed required Python libraries, including `streamlit`, `pyngrok`, `transformers`, and others.
  - Integrated **Hugging Face** models for text summarization and sentiment analysis.
  - Implemented SQLite for local storage of analyzed text data.
  - Basic implementation of text upload and processing pipeline (file upload, text processing, AI model integration).

### Week 2: September 16, 2024 - September 22, 2024
- **Feature Enhancements**:
  - Added **YAKE** for keyword extraction from uploaded texts.
  - Integrated **Gensim** for LDA topic modeling to extract themes from the text.
  - Implemented basic sentiment analysis visualizations using **Plotly**.
  - Began working on word cloud visualization using extracted themes.
  - Set up **ngrok** to run the Streamlit app publicly via Colab.

### Week 3: September 23, 2024 - September 29, 2024
- **Further Development and Fixes**:
  - Completed word cloud visualization using **WordCloud**.
  - Improved thematic relationship network using **NetworkX** to visualize the connections between extracted themes.
  - Began implementing a Q&A system (work in progress, future plans to integrate local LLM).
  - Resolved issues related to threading errors in SQLite by managing connections safely.
  - Added a number guessing game for users to engage while data is being processed.

### Week 4: (Upcoming)
- **Planned Updates**:
  - Integrate caching for faster processing of repeated requests using `@st.cache`.
  - Continue developing the Q&A functionality with a lightweight solution or predefined responses.
  - Optimize performance for larger text files and datasets.
  - Explore moving from SQLite to a more robust cloud-based database solution (e.g., Heroku PostgreSQL or AWS RDS).
  - Polish the user interface for a more seamless user experience.

---

## Installation and Setup

### 1. Set Up the Environment in Google Colab

#### a. Install Required Libraries

Run the following command to install all the required libraries:

    ```bash
    !pip install streamlit pyngrok transformers torch yake gensim nltk textblob wordcloud plotly networkx psycopg2 SQLAlchemy

#### b. Download NLTK Data
Download the required NLTK data for text processing:

    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')

### 2. Set Up ngrok for Hosting the Streamlit App

#### a. Install and Authenticate ngrok

First, install and authenticate ngrok with your token:

    ```python
    !pip install --upgrade pyngrok

Authenticate using your ngrok token:

    ```python
    from pyngrok import ngrok
    ngrok_auth_token = "YOUR_NGROK_AUTH_TOKEN"
    !ngrok authtoken {ngrok_auth_token}

#### b. Run the Streamlit App with ngrok

---

## How to Use the App

1. **Upload a Text File**:
   - Navigate to the sidebar to upload a `.txt` or `.csv` file containing your textual data.

2. **Analyze Text**:
   - Click "Analyze and Save" to analyze the text. The AI will perform:
     - Summarization.
     - Sentiment analysis.
     - Theme extraction.

3. **View Visualizations**:
   - After the analysis is complete, you can view visualizations such as:
     - **Sentiment Distribution Pie Chart**.
     - **Word Cloud** for the extracted themes.
     - **Thematic Relationship Network** using co-occurrence of themes.

---

## License

This project is licensed under the MIT License. 




