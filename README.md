# AI Spanish Learning Assistant 🇪🇸

An AI-powered full-stack Spanish learning application that provides personalized language practice through **AI conversations, flashcards, grammar quizzes, voice interaction, and progress tracking**.

The application adapts the learning experience based on the user's **CEFR proficiency level (A1–B2)** and uses Google Gemini to generate interactive learning content.

## ✨ Features

### 💬 AI Spanish Tutor

Practice Spanish through natural conversations with an AI tutor.

The tutor adapts its responses based on the selected CEFR level:

* **A1** — Beginner
* **A2** — Elementary
* **B1** — Intermediate
* **B2** — Upper Intermediate

The AI adjusts vocabulary, grammar, sentence complexity, and conversational style according to the learner's proficiency.

### 🎙️ Voice Practice

Practice conversational Spanish through voice-based interactions designed to make language learning more natural and engaging.

### 🗂️ AI-Generated Flashcards

Generate vocabulary flashcards dynamically based on the learner's:

* Selected topic
* CEFR level

Flashcards provide Spanish vocabulary, English translations, and contextual examples for practice.

### 📝 Grammar Quizzes

Practice Spanish grammar through dynamically generated exercises.

Quiz difficulty changes based on the learner's proficiency level and can cover concepts such as:

* Ser vs. estar
* Reflexive verbs
* Preterite vs. imperfect
* Por vs. para
* Present perfect
* Conditional tense
* Subjunctive
* Advanced grammar structures

### 📊 Progress Tracking

Track learning activity and progress, including information such as:

* Current CEFR level
* Practice activity
* Learning progress
* Accuracy
* Words learned

---

## 🛠️ Tech Stack

### Frontend

* React
* Vite
* JavaScript
* CSS
* Axios

### Backend

* Python
* Django
* Django REST Framework
* Django Channels

### AI

* Google Gemini
* Gemini API

### Database

* Django ORM
* SQLite for local development

---

## 🏗️ Architecture

```text id="ovdpsb"
              User
                │
                ▼
        React + Vite Frontend
                │
                │ REST API
                ▼
          Django Backend
                │
        ┌───────┼─────────┐
        │       │         │
        ▼       ▼         ▼
     Chat   Flashcards   Quizzes
        │       │         │
        └───────┼─────────┘
                │
                ▼
          Google Gemini
                │
                ▼
      Personalized Content

                +
                │
                ▼
        Progress Tracking
         Django Database
```

---

## 📁 Project Structure

```text id="lvn8gw"
ai-spanish-learning-assistant/
│
├── backend/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── spanish/
│   ├── migrations/
│   ├── admin.py
│   ├── apps.py
│   ├── consumers.py
│   ├── gemini_service.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── screens/
│   │   │   ├── ChatScreen.jsx
│   │   │   ├── FlashcardScreen.jsx
│   │   │   ├── ProgressScreen.jsx
│   │   │   ├── QuizScreen.jsx
│   │   │   └── VoiceScreen.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── manage.py
├── requirements.txt
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the Repository

```bash id="4clxcq"
git clone https://github.com/Rishitha744/ai-spanish-learning-assistant.git
cd ai-spanish-learning-assistant
```

### 2. Backend Setup

Create a virtual environment:

```bash id="c4r5mj"
python -m venv venv
```

Activate it on Windows:

```bash id="6ijz6r"
venv\Scripts\activate
```

Install the required Python packages:

```bash id="h87g6x"
pip install -r requirements.txt
```

### 3. Configure Environment Variables

Create a `.env` file in the project root.

```env id="z94pt8"
GEMINI_API_KEY=your_gemini_api_key
```

> Never commit your `.env` file or API keys to GitHub.

### 4. Set Up the Database

```bash id="8w37jo"
python manage.py migrate
```

### 5. Start the Backend

```bash id="ngprml"
python manage.py runserver
```

The Django backend will typically run at:

```text id="mxm9vb"
http://127.0.0.1:8000/
```

---

## 💻 Frontend Setup

Open another terminal:

```bash id="yy3v0a"
cd frontend
```

Install dependencies:

```bash id="87c7kn"
npm install
```

Start the Vite development server:

```bash id="7brk37"
npm run dev
```

Open the local URL displayed by Vite in your browser.

---

## 🧠 How It Works

1. The user selects a Spanish proficiency level.
2. The React frontend sends requests to the Django backend.
3. Django handles application logic and communicates with the Gemini service.
4. Gemini generates level-appropriate conversations and learning content.
5. The generated content is returned through the API.
6. The React interface presents the response to the learner.
7. Learning activity and progress can be stored through the Django backend.

---

## 🔐 Security

API keys and environment-specific configuration are stored using environment variables.

The following files should never be committed:

```text id="d63cbm"
.env
venv/
db.sqlite3
frontend/node_modules/
```

These files are excluded through `.gitignore`.

---

## 🚀 Future Improvements

* Pronunciation assessment
* Speech-to-text evaluation
* Spaced-repetition flashcards
* Personalized learning recommendations
* Expanded progress analytics
* Gamification and achievements
* Additional CEFR proficiency levels
* Support for additional languages

---

## 📄 License

This project is intended for educational and portfolio purposes.
