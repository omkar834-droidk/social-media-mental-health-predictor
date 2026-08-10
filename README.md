<div align="center">

# 🧠 Mental Health Signal
### Student Wellness Analytics — Predicting Mental Health Scores from Social Media Habits

[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](#)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](#)
[![Render](https://img.shields.io/badge/Deployed%20on-Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://render.com/)

**[🚀 Live Demo](https://social-media-mental-health-predictor-1.onrender.com)** · **[📘 API Docs](https://social-media-mental-health-predictor-1.onrender.com/docs)** · **[🐛 Report a Bug](https://github.com/omkar834-droidk/social-media-mental-health-predictor/issues)**

</div>

---

## ✨ Overview

**Mental Health Signal** is an end-to-end machine learning web app that estimates a student's wellbeing score (0–10) from their daily social media and lifestyle habits — screen time, sleep, study hours, physical activity, and perceived stress.

It's built as a full pipeline: **EDA & model training** → **FastAPI inference service** → **animated glassmorphic frontend**, all deployed live on Render.

> ⚠️ **Disclaimer:** This is a student ML project for educational purposes only. It is **not** a clinical or diagnostic tool. If you or someone you know is struggling, please talk to a real mental health professional.

---

## 🎬 Preview

| Form | Result |
|---|---|
| Colorful multi-step form with segmented stress selector | Animated gradient gauge with live score readout |

*(Add screenshots/GIFs of the running app here)*

---

## 🧰 Tech Stack

### Machine Learning
| Tool | Purpose |
|---|---|
| **Python 3.11** | Core language |
| **Pandas / NumPy** | Data wrangling & feature engineering |
| **scikit-learn** | Pipeline — `ColumnTransformer`, `OneHotEncoder`, `OrdinalEncoder`, `StandardScaler`, `FunctionTransformer` |
| **RandomForestRegressor / DecisionTreeRegressor** | Regression model for score prediction |
| **Jupyter Notebook** | EDA, feature analysis, model training & evaluation |
| **Joblib** | Model serialization (`Mental_Health_Model.pkl`) |

### Backend
| Tool | Purpose |
|---|---|
| **FastAPI** | REST API framework serving `/predict` |
| **Pydantic** | Request/response schema validation (`StudentData`, `PredictionResponse`) |
| **Uvicorn** | ASGI server |
| **CORS Middleware** | Cross-origin access for the frontend |
| **StaticFiles** | Serves the frontend directly from FastAPI |

### Frontend
| Tool | Purpose |
|---|---|
| **HTML5** | Semantic structure, form + result panels |
| **CSS3** | Glassmorphism, animated aurora background, gradient text, SVG gauge animation |
| **Vanilla JavaScript (ES6+)** | Form validation, `fetch` API calls, dynamic state management, gauge animation |
| **Google Fonts** — Fraunces, Inter, JetBrains Mono | Typography |

### Deployment
| Tool | Purpose |
|---|---|
| **Render** | Free-tier hosting for the FastAPI backend + static frontend |
| **Git / GitHub** | Version control |

---

## 📂 Project Structure

```
social-media-mental-health-predictor/
├── main.py                                  # FastAPI app — model loading, /predict endpoint, static file serving
├── Mental_Health_Model.pkl                   # Trained scikit-learn pipeline (serialized)
├── mental_health_prediction_eda_model.ipynb  # EDA, feature engineering & model training notebook
├── requirements.txt                          # Python dependencies
├── static/
│   ├── index.html                            # Frontend markup
│   ├── style.css                             # Aurora-glass animated theme
│   └── script.js                             # Form logic, validation, API calls
└── README.md
```

---

## ⚙️ Getting Started (Local Setup)

### 1. Clone the repository
```bash
git clone git@github.com:omkar834-droidk/social-media-mental-health-predictor.git
cd social-media-mental-health-predictor
```

### 2. Create a virtual environment
```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the server
```bash
uvicorn main:app --reload --port 8000
```

### 5. Open the app
Go to **http://127.0.0.1:8000/** in your browser — the FastAPI backend serves the frontend directly, so no separate server is needed.

Interactive API docs are available at **http://127.0.0.1:8000/docs**.

---

## 🔌 API Reference

### `POST /predict`

**Request body:**
```json
{
  "age": 21,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Entertainment",
  "avg_daily_usage_hours": 3.5,
  "daily_unlocks": 60,
  "study_hours": 4,
  "physical_activity_hours": 1,
  "sleep_hours_per_night": 7,
  "stress_level": "Medium"
}
```

**Response:**
```json
{
  "predicted_mental_health_score": 6.77
}
```

---

## 🚀 Deployment

This project is deployed on **[Render](https://render.com/)** as a single web service — FastAPI serves both the `/predict` API and the static frontend, so only one deployment is needed.

**Build command:**
```bash
pip install -r requirements.txt
```

**Start command:**
```bash
uvicorn main:app --host 0.0.0.0 --port $PORT
```

> Free-tier Render instances sleep after inactivity — the first request after idling may take 30–50 seconds to wake up.

---

## 🗺️ Roadmap

- [ ] Add model confidence / explainability (SHAP values)
- [ ] Persist prediction history
- [ ] Add unit tests for the `/predict` endpoint
- [ ] CI/CD pipeline for auto-deploy on push

---

## 👤 Author

**Omkar Salunke**
- GitHub: [@omkar834-droidk](https://github.com/omkar834-droidk)
- LinkedIn: [omkar-salunke](https://linkedin.com/in/omkar-salunke-712696351)

---

<div align="center">

Made with 🧠 + ☕ as part of a Data Science & AI portfolio project

</div>
