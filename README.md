# LLM Safety Router

A containerised multi-route LLM application that performs classification,
sentiment analysis, summarisation, and intent detection.  The API routes each
task to its configured model and applies input/output guardrails before
returning a response.

## Components

- `llm-multiroute` — FastAPI API, model routing, guardrails, metrics, and tests.
- `llm-frontend-python` — Flask user interface for the four analyses.
- `promptfoo-tests` and `deepeval-tests` — optional LLM evaluation suites.

## Run locally

Create a `.env` file with an Ollama API key, then run:

```bash
docker compose up --build
```

Open `http://localhost:5000`. The API documentation is available at
`http://localhost:8080/swagger-ui.html`.

## Security controls

The backend redacts secrets and personally identifiable information, records
safety events, and validates structured model output against its Pydantic
schemas. Optional environment flags can turn individual input checks into
blocking controls.

## AI-use declaration

OpenAI Codex was used to assist with project organisation, containerisation,
CI configuration, and troubleshooting. The submission owner is responsible
for reviewing and explaining the final work.
