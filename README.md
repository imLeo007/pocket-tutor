# AI Tutor Lite v1

A simple AI tutoring application where users can sign in, ask questions, and keep their previous conversations.

This was one of my first projects combining a traditional backend application with an AI model.

---

## Why I Built This

I wanted to understand how an AI feature fits inside a normal application.

Calling a model and getting a response is easy.

But a useful application also needs to answer questions like:

* Who is using the system?
* How do users sign in securely?
* How do we keep conversations separate for each user?
* Where should chat history be stored?
* How does the backend connect the user, database, and AI response together?

This project helped me understand that an AI model is only **one part of the product**.

The surrounding backend is what turns it into an application people can actually use.

---

## What the App Does

A user can:

* create an account
* sign in
* ask the AI tutor a question
* receive a generated response
* keep conversations connected to their account
* view previous chat history

Each user's conversations remain separate and are stored for later use.

---

## Application Flow

```text
User Creates Account
        ↓
User Signs In
        ↓
Authentication Confirms Identity
        ↓
User Sends a Question
        ↓
AI Generates a Response
        ↓
Question + Response Are Saved
        ↓
User Can View Previous Conversations
```

The main idea is simple:

> The AI handles the answer, while the backend handles the user, security, persistence, and application flow.

---

## Application Preview

### Login

![Login Page](screenshots/login.png)

### Tutor Chat

![Chat Page](screenshots/chat.png)

---

## Project Structure

```text
ai-tutor/
├── main.py
├── database.py
│
├── models/
│   ├── user.py
│   └── chats.py
│
├── routers/
│   ├── auth.py
│   └── chat.py
│
├── authMain.py
│
├── static/
│   ├── chat.js
│   ├── auth.js
│   └── style.css
│
├── templates/
│   ├── chat.html
│   ├── login.html
│   └── signup.html
│
├── alembic/
├── requirements.txt
└── README.md
```

The project separates authentication, chat behaviour, database models, and the small frontend so each part remains easier to understand.

---

## Main Endpoints

| Method | Endpoint        | Purpose                     |
| ------ | --------------- | --------------------------- |
| `POST` | `/auth/signup`  | Create an account           |
| `POST` | `/auth/login`   | Sign in                     |
| `POST` | `/chat/chat`    | Ask the tutor a question    |
| `GET`  | `/chat/history` | View previous conversations |

The chat routes are protected so conversation history belongs to the authenticated user.

---

## Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/imLeo007/ai-tutor-lite-v1.git
cd ai-tutor-lite-v1
```

### 2. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file:

```env
DATABASE_URL=postgresql+asyncpg://user:password@localhost/aitutor
SECRET_KEY=your_secret_key
GEMINI_API_KEY=your_api_key
```

Do not commit real secrets or API keys.

### 4. Apply database migrations

```bash
alembic upgrade head
```

### 5. Start the application

```bash
uvicorn main:app --reload
```

Open:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

---

## What I Learned

Before this project, I mainly thought about AI applications as:

```text
Question
   ↓
Model
   ↓
Answer
```

After building it, the picture became much broader:

```text
User
   ↓
Authentication
   ↓
Application Logic
   ↓
AI
   ↓
Database
   ↓
Persistent Experience
```

That was the most important lesson from this project.

The model generates the response, but the backend is responsible for making the experience reliable and personal to each user.

---

## Why This Project Matters

AI Tutor Lite became the bridge between my backend learning and the retrieval systems I started building afterward.

It taught me how to place an AI model inside a real application instead of treating the model as the whole application.

That foundation later led naturally into document retrieval, grounded answers, and RAG systems.# AI Tutor Lite v1

A simple AI tutoring application where users can sign in, ask questions, and keep their previous conversations.

This was one of my first projects combining a traditional backend application with an AI model.

---

## Why I Built This

I wanted to understand how an AI feature fits inside a normal application.

Calling a model and getting a response is easy.

But a useful application also needs to answer questions like:

* Who is using the system?
* How do users sign in securely?
* How do we keep conversations separate for each user?
* Where should chat history be stored?
* How does the backend connect the user, database, and AI response together?

This project helped me understand that an AI model is only **one part of the product**.

The surrounding backend is what turns it into an application people can actually use.

---

## What the App Does

A user can:

* create an account
* sign in
* ask the AI tutor a question
* receive a generated response
* keep conversations connected to their account
* view previous chat history

Each user's conversations remain separate and are stored for later use.

---

## Application Flow

```text
User Creates Account
        ↓
User Signs In
        ↓
Authentication Confirms Identity
        ↓
User Sends a Question
        ↓
AI Generates a Response
        ↓
Question + Response Are Saved
        ↓
User Can View Previous Conversations
```

The main idea is simple:

> The AI handles the answer, while the backend handles the user, security, persistence, and application flow.

---

## Application Preview

### Login

![Login Page](screenshots/login.png)

### Tutor Chat

![Chat Page](screenshots/chat.png)

---

## Project Structure

```text
ai-tutor/
├── main.py
├── database.py
│
├── models/
│   ├── user.py
│   └── chats.py
│
├── routers/
│   ├── auth.py
│   └── chat.py
│
├── authMain.py
│
├── static/
│   ├── chat.js
│   ├── auth.js
│   └── style.css
│
├── templates/
│   ├── chat.html
│   ├── login.html
│   └── signup.html
│
├── alembic/
├── requirements.txt
└── README.md
```

The project separates authentication, chat behaviour, database models, and the small frontend so each part remains easier to understand.

---

## Main Endpoints

| Method | Endpoint        | Purpose                     |
| ------ | --------------- | --------------------------- |
| `POST` | `/auth/signup`  | Create an account           |
| `POST` | `/auth/login`   | Sign in                     |
| `POST` | `/chat/chat`    | Ask the tutor a question    |
| `GET`  | `/chat/history` | View previous conversations |

The chat routes are protected so conversation history belongs to the authenticated user.

---

## Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/imLeo007/ai-tutor-lite-v1.git
cd ai-tutor-lite-v1
```

### 2. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file:

```env
DATABASE_URL=postgresql+asyncpg://user:password@localhost/aitutor
SECRET_KEY=your_secret_key
GEMINI_API_KEY=your_api_key
```

Do not commit real secrets or API keys.

### 4. Apply database migrations

```bash
alembic upgrade head
```

### 5. Start the application

```bash
uvicorn main:app --reload
```

Open:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

---

## Why This Project Matters

AI Tutor Lite became the bridge between my backend learning and the retrieval systems I started building afterward.

It taught me how to place an AI model inside a real application instead of treating the model as the whole application.

That foundation later led naturally into document retrieval, grounded answers, and RAG systems.

---

## Final Note

AI Tutor Lite is intentionally small.

The goal was not to build a complete education platform.

The goal was to understand the foundations of an AI-powered application:

> identify the user, protect their data, connect them to the model, and preserve their experience over time.

That understanding became the starting point for the more advanced AI backend systems I built next.

---

## Links

**GitHub Repository:**
https://github.com/imLeo007/ai-tutor-lite-v1

**LinkedIn:**
https://www.linkedin.com/in/mariya-raju-akumarthi-687354417


---

## Final Note

AI Tutor Lite is intentionally small.

The goal was not to build a complete education platform.

The goal was to understand the foundations of an AI-powered application:

> identify the user, protect their data, connect them to the model, and preserve their experience over time.

That understanding became the starting point for the more advanced AI backend systems I built next.

---

## Links

**GitHub Repository:**
https://github.com/imLeo007/ai-tutor-lite-v1

**LinkedIn:**
https://www.linkedin.com/in/mariya-raju-akumarthi-687354417
