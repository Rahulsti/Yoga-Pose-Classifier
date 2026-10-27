# Yoga Pose Classifier 🧘

A deep-learning web app that identifies yoga poses from a photo. Upload an image and the model predicts the pose, shows how confident it is, and charts the probability for every pose it knows.

## Poses recognised

Downward Dog · Goddess · Plank · Tree · Warrior II

## How it works

1. **Model:** a convolutional neural network built on **MobileNetV2** using transfer learning, trained on images of the five poses and saved as `yoga_pose_model.h5`.
2. **Preprocessing:** the uploaded image is resized to 224 × 224 and its pixel values are scaled to 0–1.
3. **Prediction:** the model outputs a probability for each pose, and the highest one is the prediction.
4. **Confidence check:** if the top probability is below 90%, the app says it doesn't recognise the pose instead of guessing.
5. **Results:** the predicted pose, its confidence score, and a bar chart of every pose's probability.

## Tech stack

Python · TensorFlow / Keras · MobileNetV2 · Streamlit · NumPy · Pandas · Pillow

## Running it locally

```bash
git clone https://github.com/Rahulsti/Yoga-Pose-Classifier.git
cd Yoga-Pose-Classifier
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt.txt
streamlit run app.py
```

Then open the URL Streamlit prints (usually http://localhost:8501), upload a photo and click **Classify Pose**.

Use Python 3.11. TensorFlow 2.15 does not support newer Python versions.

## Project structure

| File | Purpose |
| --- | --- |
| `app.py` | Streamlit app: loads the model, preprocesses the image, predicts and shows the results |
| `yoga_pose_model.h5` | Trained MobileNetV2-based Keras model |
| `requirements.txt` | Python dependencies |
| `packages.txt` | System packages for deployment |
| `runtime.txt` | Python version for deployment |
