# FastAPI OpenAI Practice API

A simple practice project for building AI-powered API endpoints using **Python**, **FastAPI**, and the **OpenAI API**.

This project exposes several AI endpoints for:

- Text summarization
- Translation
- Title generation
- Code explanation

---

## Getting Started

1. Create and activate a Python virtual environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the project root with your OpenAI API key:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

4. Start the app:

```bash
uvicorn app.main:app --reload
```

5. Open the API docs in your browser:

```text
http://127.0.0.1:8000/docs
```

---

## API Endpoints

### `GET /`

Returns a simple health check message.

### `POST /summarize`

Request body:

```json
{
  "text": "Long text to summarize...",
  "style": "simple"
}
```

Response:

```json
{
  "summary": "A concise summary..."
}
```

### `POST /translate`

Request body:

```json
{
  "text": "Text to translate...",
  "target_language": "French"
}
```

Response:

```json
{
  "translation": "Texte traduit..."
}
```

### `POST /generate-title`

Request body:

```json
{
  "text": "Text to generate titles from...",
  "count": 5
}
```

Response:

```json
{
  "titles": "1. Title idea one\n2. Title idea two..."
}
```

### `POST /explain-code`

Request body:

```json
{
  "code": "print(\"Hello world\")",
  "language": "python"
}
```

Response:

```json
{
  "explaination": "Explanation of the code..."
}
```

---

## Project Structure

```text
fastapi-ai-api/
│
├── app/
│   ├── main.py
│   ├── openai_service.py
│   └── schemas.py
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Notes

- The project uses `openai` with the responses API and `gpt-4.1-mini`.
- Validation is handled by Pydantic models defined in `app/schemas.py`.
- If you update your `.env`, restart the app to apply changes.
