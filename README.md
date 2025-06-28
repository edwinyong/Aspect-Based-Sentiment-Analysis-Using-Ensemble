# 📊 Enhanced Aspect-Based Sentiment Analysis (ABSA) - User Manual

This project provides an enhanced Aspect-Based Sentiment Analysis (ABSA) system using deep learning (BiLSTM, GRU, etc.) and a Flask-based web application for easy access and deployment.

---

## 📁 Project Structure

```
project/
│
├── Enhanced_ABSA.ipynb       # Jupyter Notebook for training & testing ABSA models
├── FlaskApps.ipynb           # Flask-based web app for model inference
├── models/                   # Trained model files
├── static/                   # Static files (CSS, JS)
├── templates/                # HTML templates for Flask
├── requirements.txt          # Required Python packages
└── README.md                 # This user manual
```

---

## 🔧 Installation Guide

### 🐍 1. Environment Setup

Use `conda` or `venv`:

```bash
# Create virtual environment
python -m venv absa-env
source absa-env/bin/activate     # On Windows: absa-env\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

Make sure the following are included in `requirements.txt`:

```
flask
torch
transformers
pandas
scikit-learn
numpy
```

---

## 🧠 Training ABSA Models

### 1. Open the Notebook

Launch `Enhanced_ABSA.ipynb` in Jupyter or VS Code.

### 2. Dataset

Prepare your dataset in CSV format:
- Required columns: `text`, `label`, `aspect` (or similar)
- Drop in the correct location and update the notebook path.

### 3. Run Training

Run the cells step-by-step to:
- Preprocess text
- Tokenize & encode
- Train deep learning models (BiLSTM, GRU, etc.)
- Save trained models to `/models/`

---

## 🌐 Running the Web App

### 1. Run Flask App

You can either:
- Export `FlaskApps.ipynb` to `.py`, or
- Run it via Jupyter with:

```python
!flask run
```

Or from command line:

```bash
python FlaskApps.py
```

### 2. Access the Web Interface

Once Flask is running, open your browser and go to:

```
http://127.0.0.1:5000/
```

---

## ✅ How to Use

1. Input a sentence in the text box.
2. The system will predict the sentiment **for each aspect**.
3. Results will be displayed with corresponding **sentiment labels** (Positive, Negative, Neutral).

---

## 💡 Customizing Aspects

You can add or edit the aspect categories by modifying the `ASPECT_SEEDS` or `aspects` list inside `Enhanced_ABSA.ipynb` or `FlaskApps.ipynb`.

Example:
```python
aspects = ["usability", "performance", "pricing", "features"]
```

---

## 📦 Deployment (Optional)

To deploy this on a cloud platform like **Render**, **Heroku**, or **AWS EC2**, follow the platform's Flask deployment guide and ensure:
- `app.py` exists and runs the Flask app
- `requirements.txt` is accurate
- A `Procfile` is added (for Heroku):

```
web: python app.py
```

---

## 🔧 Troubleshooting

| Problem                   | Solution                                             |
|--------------------------|------------------------------------------------------|
| `ModuleNotFoundError`    | Check your `requirements.txt` and re-install deps    |
| Model not found          | Ensure models are trained and saved to `/models/`    |
| Flask app not loading    | Check if port 5000 is available                      |
| Prediction wrong/missing | Recheck your aspect list & tokenizer pipeline        |

---

## 📬 Contact

For issues or contributions, feel free to open an issue or pull request.
