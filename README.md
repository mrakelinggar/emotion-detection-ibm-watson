# **Emotion Detection Web App**
A Flask‑based web application that analyzes text and identifies the dominant emotion using IBM Watson’s NLP Emotion Prediction API.

## **📌 Overview**
This project demonstrates how to integrate a cloud‑based NLP model into a Python web application. Users enter any text into a simple web interface, and the system returns emotion scores for **anger, disgust, fear, joy, and sadness**, along with the **dominant emotion**.

It’s a clean example of:
- API consumption in Python
- JSON parsing and error handling
- Flask routing and request handling
- Front‑end to back‑end integration
- Unit testing for NLP outputs

---

## **🚀 Features**
- Web interface built with Flask
- Real‑time emotion detection using IBM Watson NLP
- Cleanly formatted output summarizing all emotion scores
- Graceful handling of invalid or empty input
- Modular code structure (`emotion_detector()` separated from Flask app)
- Full unit test suite validating dominant emotion detection

---

## **🧠 How It Works**
1. User enters text into the web form.
2. Flask sends the text to the `emotion_detector()` function.
3. The function calls IBM Watson’s EmotionPredict API with the text.
4. The API returns a JSON payload containing emotion scores.
5. The app extracts:
   - Individual emotion scores
   - The dominant emotion
6. The result is formatted into a human‑readable sentence and displayed to the user.

---

## **📂 Project Structure**
```
emotion-detection-ibm-watson/
│
├── EmotionDetection/
│   └── emotion_detection.py     # Core logic calling IBM Watson API
│
├── templates/
│   └── index.html               # Web UI
│
├── server.py                    # Flask application
├── test_emotion_detection.py    # Unit tests
└── README.md                    # Project documentation
```

---

## **🧪 Unit Testing**
The project includes a full test suite using Python’s `unittest` framework.

Test cases include:
- Joy
- Anger
- Disgust
- Sadness
- Fear

Each test verifies that the correct **dominant emotion** is returned for a given input sentence.

Run tests with:

```bash
python3 -m unittest test_emotion_detection.py
```

---

## **▶️ Running the Application**
Start the Flask server:

```bash
python3 server.py
```

Then open your browser and navigate to:

```
http://localhost:5000
```

Enter any text and the system will return the emotion scores and dominant emotion.

---

## **🌐 API Used**
This project uses IBM Watson’s **EmotionPredict** model:

- Endpoint:
  `https://sn-watson-emotion.labs.skills.network/v1/watson.runtime.nlp.v1/NlpService/EmotionPredict`

- Model ID:
  `emotion_aggregated-workflow_lang_en_stock`

The API returns a structured JSON response containing both global and span‑level emotion scores. This project uses the **global scores**, which represent the overall emotional tone of the text.

---

## **🛠️ Technologies Used**
- Python 3
- Flask
- Requests
- IBM Watson NLP API
- HTML/CSS
- Unittest

---

## **🏫 Skills Network Theia Lab Environment**

This project was developed and executed entirely within the **Skills Network Theia Lab** environment provided by IBM Skills Network. The EmotionPredict API used in this application is **hosted on the Skills Network platform** and is **only accessible from within the Theia Lab environment**.  

Because of this:

- The API **cannot be accessed from local IDEs** such as VS Code, PyCharm, or Jupyter running on local machine.  
- The Flask application and all unit tests must be run **inside the Theia Lab workspace** for the API calls to succeed.  
- Attempting to run the project locally will result in connection errors, since the endpoint is not publicly available.

This setup ensures a controlled, sandboxed environment for learning and experimentation with IBM Watson NLP services.

---

