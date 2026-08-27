# Emotion Detection Application

Final project for the IBM AI Developer coursework.

This project implements an AI-based emotion detection web application using Watson NLP and Flask.

## Features

- Detects anger, disgust, fear, joy, and sadness
- Returns the dominant emotion
- Exposes a Flask web interface
- Handles invalid or blank input
- Includes unit tests
- Follows PEP 8 conventions

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
