## SentimentPulse - Sentiment Analysis Telegram Bot

### Introduction
SentimentPulse is an advanced Telegram bot designed for collecting user feedback and analyzing the sentiment of the feedback using Natural Language Processing (NLP). The bot integrates Python (with FastAPI) for NLP tasks and JavaScript (with Telegraf.js) for managing Telegram bot functionalities. By leveraging a pre-trained NLP model, SentimentPulse can accurately determine the sentiment of the provided feedback.

### Features
- **Feedback Submission**: Users can effortlessly submit their feedback through the bot.
- **Text Preprocessing**: The bot preprocesses incoming feedback to prepare it for analysis.
- **Sentiment Analysis**: SentimentPulse utilizes a pre-trained NLP model to classify the feedback as positive, negative, or neutral.
- **Data Storage**: All user feedback and sentiment data are securely stored in a MongoDB database using Mongoose.

### Prerequisites
To run SentimentPulse, ensure you have the following software installed:
- **Python**: Needed to execute `app.py` and `train_model.py`.
- **Node.js**: Required to run the Telegram bot scripts.
- **MongoDB**: Used for storing user feedback and sentiment data.

### Training the NLP Model
Before deploying the bot, you need to train the NLP model and generate the `sentiment_model_pipeline.pkl` file.

1. **Prepare Training Data**: Save your training data in the `training_data.csv` file. This file should include a `feedback` column for the feedback text and a `label` column for the sentiment labels (positive/negative/neutral).
2. **Train the Model**: Run the `train_model.py` script to train the model and create the `sentiment_model_pipeline.pkl` file.

```bash
python train_model.py
```

### Usage

#### Step 1: Start the Python NLP API
Launch the FastAPI server to handle NLP tasks by running `app.py`.

```bash
python app.py
```

The API will be accessible at `http://127.0.0.1:8000`.

#### Step 2: Start the Telegram Bot
Navigate to the bot directory and start the Telegram bot using Telegraf.js by running `bot.js`.

```bash
cd bot
node bot.js
```

The bot will become active on Telegram, ready to respond to user commands and collect feedback.

#### Step 3: Interacting with the Telegram Bot
1. **Activate the Bot**: Find the bot on Telegram and start a conversation by sending a message.
2. **Submit Feedback**: The bot will prompt you to provide feedback.
3. **Sentiment Prediction**: Upon receiving feedback, the bot will process the text, predict the sentiment, and notify you of the result.
4. **Data Storage**: The feedback and its sentiment analysis will be saved in the MongoDB database.

---
