## Run locally

### Option A: Using uv (recommended)
1) Create and activate a local venv
```bash
uv venv --python 3.12
source .venv/bin/activate
```
2) Install deps
```bash
uv sync
```
3) Set your API key (or use a `.env` file with `OPENAI_API_KEY=...`)
```bash
export OPENAI_API_KEY="sk-..."
```
4) Start the server
```bash
uv run uvicorn api.index:app --reload --host 0.0.0.0 --port 8000
```
Open http://localhost:8000

### Option B: Using venv + pip
1) Create and activate venv
```bash
python3 -m venv .venv
source .venv/bin/activate
```
2) Install deps
```bash
pip install -r api/requirements.txt
```
3) Set your API key (or use a `.env` file with `OPENAI_API_KEY=...`)
```bash
export OPENAI_API_KEY="sk-..."
```
4) Start the server
```bash
uvicorn api.index:app --reload --host 0.0.0.0 --port 8000
```
Open http://localhost:8000

Notes:
- You can place a `.env` file at the repo root with `OPENAI_API_KEY=...`.
- The app entrypoint is `api/index.py` (FastAPI). Vercel deploy uses the same file.

