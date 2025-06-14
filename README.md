# OliverAI Enhanced

This repository contains a lightweight AI backend powered by Google's Gemini models.
It exposes a FastAPI application for retrieval–augmented generation (RAG) and includes
a small script for directly calling the Gemini API.

## Structure

- `ai_backend/` - FastAPI application for RAG operations powered by Gemini and Supabase Vector.
- `.env.example` - Example environment variables required to run the backend.
- `scripts/gemini_demo.py` – Simple script that calls the Gemini API using your key.

Copy `.env.example` to `.env` and fill in your credentials before starting the
server.

## Setup

1. Clone this repository and install the required Python packages. If your
   environment does not have internet access, download the wheels on another
   machine and place them in a `wheelhouse` directory first.

```bash
pip install --no-index --find-links wheelhouse -r ai_backend/requirements.txt
```

2. Copy `.env.example` to `.env` and fill in the following values:

```bash
GEMINI_API_KEY=your_gemini_key
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your-supabase-service-key
```

The clients are configured to use REST transport by default, which avoids common
TLS issues when running behind proxies.

## Running the server

Start the FastAPI application with Uvicorn:

```bash
uvicorn ai_backend.app.main:app --reload
```

The server exposes endpoints for document processing and question answering.

If you need to generate the wheelhouse directory on a machine with internet
access, run:

```bash
pip download -d wheelhouse -r ai_backend/requirements.txt
```

## Running the demo script

After configuring your API key you can test direct Gemini access:

```bash
export GEMINI_API_KEY=your_gemini_key
python scripts/gemini_demo.py
```

It should print a short greeting returned by the model.


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

