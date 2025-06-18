# 🧑‍🏫 TDS Virtual TA

A virtual teaching assistant for the IIT Madras **Tools in Data Science (TDS)** course that automatically answers student questions using course content and Discourse discussions.

![FastAPI](https://img.shields.io/badge/FastAPI-virtual--ta-green?logo=fastapi)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-blue?logo=openai)
![License](https://img.shields.io/github/license/your-repo/tds-virtual-ta)

---

## 🚀 Features

- ✅ Uses OpenAI's GPT model via **AI Proxy**
- ✅ Answers student questions using:
  - TDS course materials (`markdown_chunks`)
  - Optionally: Discourse discussions (`discourse_chunks`)
- ✅ Embeds and retrieves context using `text-embedding-3-small`
- ✅ Returns a clean JSON response:
  ```json
  {
    "answer": "Concise answer...",
    "links": [
      { "url": "https://...", "text": "Relevant reference" }
    ]
  }
