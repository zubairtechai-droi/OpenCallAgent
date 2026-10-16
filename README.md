# OpenCallAgent
An open-source AI voice agent that talks to customers, books appointments and saves every call to a CRM.



An open-source AI voice agent that answers calls, qualifies leads, books appointments and logs everything to your CRM. Built with free tools only ($0).



# Why this project

Small businesses miss calls and lose leads because call centers and paid voice platforms are expensive. Awaaz AI shows that a low-latency voice agent can be built entirely with free and open-source software.

# Features
Real-time voice conversation with interruption handling (barge-in)
Target latency under 1.5 seconds from end of speech to first audio
Lead qualification and scoring
Appointment booking with correct timezone handling (stored in UTC)
Knowledge-base answers using RAG (LlamaIndex)
Short-term memory (per call) and long-term memory (per customer)
CRM sync through n8n webhooks
Human handoff when the caller asks or the agent is unsure
Tracing and debugging (LangSmith free tier or Langfuse)
Prompt injection defenses and tool-argument validation
Multilanguage support



## Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Languages | Python, JavaScript/TypeScript | Backend, agent and ML in Python; frontend in JS/TS |
| Frontend | Next.js (React), Tailwind CSS, LiveKit React components | Web app for callers and admin dashboard |
| Backend API | FastAPI | LiveKit tokens, webhooks, call history API |
| Database | PostgreSQL + pgvector | Customers, call logs, bookings, memory, embeddings |
| Browser calls | WebRTC | Free real-time audio, no phone number needed |
| Audio server | LiveKit | Real-time audio rooms and agent dispatch |
| Voice agent | LiveKit Agents (Python) | Runs the live conversation pipeline |
| Voice activity detection | Silero VAD | Detects when the caller stops speaking |
| Speech-to-text | faster-whisper | Transcribes caller audio |
| LLM | Groq free tier or Ollama | Reasoning and replies |
| Text-to-speech | Piper or Kokoro | Agent voice output |
| Agent logic and memory | LangChain, LangGraph | Tools, state and short-term memory |
| RAG | LlamaIndex, BGE embeddings | Answers from business documents |
| Machine learning | scikit-learn, XGBoost, Hugging Face Transformers, sentence-transformers | Lead scoring, intent, sentiment, injection detection, clustering |
| ML training | Google Colab, Kaggle | Free GPU notebooks |
| Automation | n8n (Docker) | Webhooks, CRM sync, reminders |
| CRM | HubSpot Free (or Twenty / EspoCRM) | Leads and call outcomes |
| Observability | LangSmith or Langfuse | Traces and latency monitoring |
| Testing | pytest, promptfoo | Timezone, tools, memory and prompt injection tests |
| Containers | Docker, Docker Compose | Reproducible setup |
| Backend hosting | Oracle Cloud Always Free VM | Runs API, agent, Postgres and n8n |
| Frontend hosting | Vercel free tier or Cloudflare Pages | Free public URL |
| Public webhooks | Cloudflare Tunnel | Exposes local services securely |
| Secure access | SSH ProxyJump or Tailscale | Jump server |
| Version control | Git, GitHub | Code and portfolio |
| Telephony (optional, paid) | SIP via Twilio or Telnyx | Real phone numbers, added only when a client needs it |

> **Software cost: $0** when using browser (WebRTC) calls.
