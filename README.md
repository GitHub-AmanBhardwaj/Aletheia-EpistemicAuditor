# Aletheia — Epistemic Auditor

Aletheia is an automated, multi-agent Natural Language Inference (NLI) framework designed to detect stochastic parroting and epistemic hallucinations in scientific literature.

## Demo Video

Watch the application in action:

https://drive.google.com/file/d/1Xh0SPo2OawKlU04Cak2VJ5L48SmYPbGt/view

---

## Run Locally with Docker

The application is available as a pre-built Docker image that you can pull and run locally.

### Prerequisites

- Docker installed
- Docker Desktop with the **containerd image store** enabled (required for pulling Hugging Face Space images)

### Run

```bash
docker run -it -p 7860:7860 --platform=linux/amd64 \
  -e SECRET_KEY="YOUR_SECRET_KEY" \
  -e GOOGLE_CLIENT_ID="YOUR_GOOGLE_CLIENT_ID" \
  -e GOOGLE_API_KEY_1="YOUR_GOOGLE_API_KEY_1" \
  -e GOOGLE_API_KEY_2="YOUR_GOOGLE_API_KEY_2" \
  -e SESSION_COOKIE_SECURE="False" \
  -e USE_MOCK_DATA="False" \
  -e MAX_UPLOAD_MB="50" \
  registry.hf.space/whyamanbhardwaj-aletheia:latest
```

Once the container starts, open:

```
http://localhost:7860
```

### Required Environment Variables

| Variable | Description |
|----------|-------------|
| `SECRET_KEY` | Secret key used for session security |
| `GOOGLE_CLIENT_ID` | Google OAuth Client ID |
| `GOOGLE_API_KEY_1` | Primary Google Gemini API key |
| `GOOGLE_API_KEY_2` | Secondary/backup Google Gemini API key |
| `SESSION_COOKIE_SECURE` | Set to `False` for local development |
| `USE_MOCK_DATA` | Set to `False` to use the production pipeline |
| `MAX_UPLOAD_MB` | Maximum upload size (MB) |

---

## Live Application

Try the hosted application:

https://whyamanbhardwaj-aletheia.hf.space/
