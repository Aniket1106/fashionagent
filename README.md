# fashionAgent

A lightweight FastAPI-based fashion assistant service.

## Repository structure

- `main.py` - entrypoint for starting the FastAPI app.
- `dockerfile` - Docker image definition.
- `compose.yaml` - compose definition for local multi-service startup.
- `requirements` - Python dependencies list.

- `src/`
  - `app/`
    - `routers/route.py` - API routes.
    - `schema/` - Pydantic request/response schema models.
    - `service/agentService.py` - business logic and domain service operations.
    - `utils/` - helper utilities.
  - `db/db.py` - database connection helper(s).
  - `middleware/auth.py` - authentication/authorization middleware.
  - `model/llm.py` - LLM adapter integration.

- `certs/` - TLS certificates.
- `migration/` - DB migration scripts.

## Development

1. Create and activate Python virtual environment.

```bash
python -m venv .venv
.venv/Scripts/activate
pip install -r requirements
```

2. Run app locally:

```bash
python main.py
```

3. (Optional) Run in Docker:

```bash
docker build -t fashionagent -f dockerfile .
docker run -p 8000:8000 fashionagent
```

## Notes

- Validate `compose.yaml` and `dockerfile` naming/paths if running container setup.
- Update `src/config/chatbotSchema.py` with your environment-specific settings for LLM/chatbot.

## Contact

For issues or enhancements, open a GitHub issue in your repository or reach out to your project team.