# Repository for final project

## Project Name
Final Project: Emotion Detection Application

This project uses the Watson NLP library to detect emotions in text and is deployed as a web application using Flask.

## Features
- Detects anger, disgust, fear, joy, and sadness
- Identifies the dominant emotion
- Flask web application
- Error handling for invalid input
- Unit testing
- Pylint static code analysis
  
## Project structure

```text
EmotionDetection/
├── __init__.py
└── emotion_detection.py
static/
└── mywebscript.js
templates/
└── index.html
server.py
test_emotion_detection.py
README.md
```

## Run

```bash
python3 server.py
```

Then open the URL exposed by the lab environment.
