# ML Voice ID Classifier

A Python machine learning project that identifies who is speaking based on audio input.  
Uses feature extraction from `.wav` files and a scikit-learn classifier, with a simple GUI for real-time prediction.

---

## What This Does

1. Extracts audio features from speech recordings
2. Trains a voice classification model
3. Runs a GUI that listens to audio and predicts the speaker (with % confidence)

A pre-trained model is included, but this project is designed to be **re-trained with your own voices**.

---

## Project structure

data/audio/raw        -> your .wav files
data/audio/processed  -> extracted features
notebooks/            -> model training
src/speech_rec/       -> main application

## Requirements

- Python 3.10+
- scikit-learn
- numpy, pandas
- tkinter (GUI)

## Setup
1. Clone Repo
2. Install dependencies:
```bash
pip install .
```
3. Record your own audio files:
```bash
python3 -m src.speech_recognition.utils.record_audio --speaker <yourname> --session <sessionID> --duration <duration>
 ```
* For example -> python3 -m src.speech_recognition.utils.record_audio --speaker David --session 01 --duration 180. 
* record each person multiple times (5 or more recordings per person / ~ 5-10 min per recording)
* record in quiet room and speak clearly and at a good volume

4. Convert Audio -> CSV file for model
```bash
python3 -m src.speech_recognition.utils.extract_audio_features
```
5. Train the model:
* open jupyter notebook
```bash
jupyter notebook
```
* choose notebooks/speech_rec.ipyb
* update name encodings in 2nd Cell
* run all cells

6. Run live predictor:
* update encoding -> name mapping in main.py & then run predictor
```bash
python3 -m src.speech_recognition
```
7. Speak and watch the magic!!
