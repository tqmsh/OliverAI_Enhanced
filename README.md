# OliverAI Enhanced

This repository contains the AI backend implementation focused on Google's Gemini models.

## Structure

- `ai_backend/` - FastAPI application for RAG operations powered by Gemini and Supabase Vector.
- `.env.example` - Example environment variables required to run the backend.

Copy `.env.example` to `.env` and fill in your credentials before starting the
server.

## Usage

Install dependencies and run the server. If the environment does not have
internet access, pre-download the required wheels on another machine and copy
them to a local directory (`wheelhouse`). Then run:

```bash
pip install --no-index --find-links wheelhouse -r ai_backend/requirements.txt
uvicorn ai_backend.app.main:app --reload
```

The `wheelhouse` directory should contain wheel files for all dependencies.
Generate it on a machine with internet access using:

```bash
pip download -d wheelhouse -r ai_backend/requirements.txt
```


## Testing

Run the unit tests using pytest. Ensure dependencies are installed from your wheelhouse first.

```bash
pip install --no-index --find-links wheelhouse -r ai_backend/requirements.txt
pytest -q
```

## Cloning and Updating

This repository is intended to be pulled like any standard Git project:

```bash
git clone <repository-url>
cd OliverAI_Enhanced
git pull
```

If you do not see the latest files after pulling, ensure you are on the `main`
branch using `git checkout main` before running `git pull`.

