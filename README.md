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


📦 API Usage
Endpoint

POST /api/
Request Format
json
Copy
Edit
{
  "question": "Should I use Docker or Podman?",
  "image": "<optional base64 image>"
}
Response Format
json
Copy
Edit
{
  "answer": "Use Docker as shown in the official setup guide.",
  "links": [
    {
      "url": "https://tds.s-anand.net/#/docker",
      "text": "Official Docker/Podman setup guide for TDS course"
    }
  ]
}
🛠 Setup Instructions
1. Clone the repository

git clone https://github.com/your-username/tds-virtual-ta.git
cd tds-virtual-ta
2. Install dependencies

pip install -r requirements.txt
3. Set your environment variables
Create a .env file in the project root:


AIPROXY_TOKEN=your_openai_or_proxy_key
⚠️ This token must work with the AI Proxy server.

4. Add the knowledge base
Ensure knowledge_base.db is present in the project root. It should contain:

markdown_chunks (TDS course content)

Optionally discourse_chunks (if enabled)

Use the scraping script provided in scripts/ (if available) to generate this.

5. Run the FastAPI app

uvicorn app:app --reload --port 8000
Now your API will be live at:


http://localhost:8000/api/
🌐 Deployment
You can deploy this app on platforms like:

🔷 Render

🟡 Railway

🔵 Replit

🟠 Ngrok (temporary, use for testing only)

Make sure to include your .env variables on the platform.

✅ Project Structure

tds-virtual-ta/
├── app.py               # Main FastAPI app
├── knowledge_base.db    # Precomputed embeddings
├── .env                 # API keys
├── requirements.txt     # Dependencies
├── README.md            # This file
🧪 Evaluation Instructions
To test with promptfoo, update the YAML config:


providers[0].config.url: https://your-deployment-url/api/
Run:

npx -y promptfoo eval --config project-tds-virtual-ta-promptfoo.yaml
📜 License
This project is licensed under the MIT License. See LICENSE for details.

🙌 Contributors
Made with ❤️ for the IITM BS in Data Science course project – by students, for students.

