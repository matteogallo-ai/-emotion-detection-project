"""Emotion detection using the Watson NLP emotion service."""

import requests


EMOTION_URL = (
    "https://sn-watson-emotion.labs.skills.network/"
    "v1/watson.runtime.nlp.v1/NlpService/EmotionPredict"
)
HEADERS = {
    "grpc-metadata-mm-model-id":
    "emotion_aggregated-workflow_lang_en_stock"
}


def emotion_detector(text_to_analyze):
    """Return emotion scores and the dominant emotion for input text."""
    input_json = {"raw_document": {"text": text_to_analyze}}
    response = requests.post(
        EMOTION_URL,
        json=input_json,
        headers=HEADERS,
        timeout=30,
    )

    if response.status_code == 400:
        return {
            "anger": None,
            "disgust": None,
            "fear": None,
            "joy": None,
            "sadness": None,
            "dominant_emotion": None,
        }

    response_data = response.json()
    emotions = response_data["emotionPredictions"][0]["emotion"]

    return {
        "anger": emotions["anger"],
        "disgust": emotions["disgust"],
        "fear": emotions["fear"],
        "joy": emotions["joy"],
        "sadness": emotions["sadness"],
        "dominant_emotion": max(emotions, key=emotions.get),
    }
