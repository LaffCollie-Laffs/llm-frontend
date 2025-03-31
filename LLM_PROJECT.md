# 💻 LLM Project Summary

## 🧠 Setup Overview

### Backend
- Hosted on: DigitalOcean Droplet (Ubuntu)
- Framework: FastAPI
- Auth: Token-based (static token via `.env`)
- Deployed as: Systemd service (`llm-backend.service`)
- Storage:
  - `.env`: All API keys + auth token
  - `quota.json`: Daily quota per provider
  - `usage.json`: Usage tracked per day per provider
  - `logs.txt`: Logs of all requests with timestamp, model, prompt, and output

### Providers Supported
- ✅ OpenAI (`gpt-3.5-turbo`)
- ✅ Anthropic (`claude-3-haiku-20240307`)
- ✅ Mistral (`mistral-tiny`)
- ✅ TogetherAI (`Mixtral-8x7B`)

### CLI Tools (via Bash Wrapper)
- `prompt`: Send prompt via CLI
- `model-diff`: Send same prompt to all models and compare outputs
- `logs`: Tail last 50 log entries
- `logs-all`: View full logs via `less`
- `usage`: View usage for all providers or a specific one

All CLI tools respect the API token and dynamically update after usage.

### Frontend
- Hosted on: GitHub Pages (`frontend.chaudhurisolutions.com`)
- Supports:
  - Prompt input
  - Model selection
  - Response output
  - Reset button
  - Usage dashboard with emoji, quotas, warnings

---

## 🚧 Roadmap (As of Now)

### ✅ Completed
- Multi-provider backend + frontend dropdown
- Real-time usage tracking with quota enforcement
- CLI utilities with alias (`llm`) and `prompt`, `usage`, etc.
- Frontend usage dashboard with dynamic updates
- Hooks for future `enhance_prompt()` and `rejig_response()` logic

### 🔜 In Progress / Next

#### 1. Searchable Logs UI
- `/logs` route exists
- Need frontend page to:
  - Display last 50 (or more) entries
  - Filter by provider/date/content

#### 2. Multi-Model Support Per Provider
- Frontend model dropdown needs to support:
  - e.g. `gpt-3.5`, `gpt-4`, `claude-3-haiku`, `claude-3-opus`
- Backend will route payloads accordingly

#### 3. Frontend Styling & Branding
- Improve layout, spacing, and mobile experience
- Add simple branding (favicon/logo)
- Consider Tailwind CSS or minimal styling refresh

---

## 🛠 Developer Tools
- Editor: `nano` (preferred), `micro` installed
- SSH: PuTTY from Windows
- Git: GitHub repo used for `frontend`
- Domain: Managed via Squarespace
  - Backend: `api.chaudhurisolutions.com`
  - Frontend: `frontend.chaudhurisolutions.com`

---


