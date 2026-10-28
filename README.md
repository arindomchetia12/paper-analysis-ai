# Paper to Prototype

A single-file Flask app that reads uploaded PDF/TXT/Markdown research, asks GPT to find evidence-backed product gaps, then uses GPT to create a self-contained HTML prototype that can be previewed and downloaded.

## Setup

```powershell
cd path\to\paper-to-prototype
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python app.py
```

Open http://127.0.0.1:8000. Add your OpenAI API key, upload papers, click **Analyze papers**, then click **Build prototype**.

Set `OPENAI_MODEL` to select another model that supports the Responses API. The default is `gpt-4.1`.

Paper text and your API key are sent to OpenAI for analysis and generation. The app does not save them. Keep this local preview bound to localhost; do not expose it publicly without authentication, rate limits, and managed secrets. Scanned PDFs without a text layer may not extract well. Review generated HTML before running a downloaded prototype. Physical products are not fabricated by the app.
