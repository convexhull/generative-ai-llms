🧠 GenAI for LLP Tasks

This repository contains Jupyter Notebooks with generative AI utilities tailored for business and commercial workflows. It includes modular notebooks for:

📝 Website summarization

📧 Email subject line suggestion

🧾 More upcomming...

Each notebook uses locally running LLMs via Ollama or cloud models via the Frontier API for flexible experimentation.

## Setup Instructions

### Prerequisites

1. **Install UV** (Python package manager):
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```
   
   Or on macOS using Homebrew:
   ```bash
   brew install uv
   ```

2. **Verify UV installation**:
   ```bash
   uv --version
   ```

### Environment Setup

1. **Clone the repository** (if you haven't already):
   ```bash
   git clone <your-repo-url>
   cd generative-ai-llms
   ```

2. **Create and activate UV environment**:
   ```bash
   uv sync
   ```
   This will:
   - Create a virtual environment
   - Install Python 3.11 (as specified in `.python-version`)
   - Install all dependencies from `pyproject.toml`

3. **Set up your environment variables**:
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` and add your OpenAI API key:
   ```
   OPENAI_API_KEY=sk-proj-your-actual-api-key-here
   ```

### Running Notebooks

1. **Start Jupyter Notebook**:
   ```bash
   uv run jupyter notebook
   ```
   
   Or use JupyterLab:
   ```bash
   uv run jupyter lab
   ```

2. **Run a specific notebook**:
   ```bash
   uv run jupyter notebook brochure_generator.ipynb
   ```

### Running Notebooks with Ollama

For notebooks that use Ollama (local LLM):

1. **Install Ollama**: Visit [ollama.ai](https://ollama.ai) and follow installation instructions

2. **Pull the required model**:
   ```bash
   ollama pull llama3.2
   ```

3. **Start Ollama server** (usually starts automatically):
   ```bash
   ollama serve
   ```

### Available Notebooks

- `brochure_generator.ipynb` - Generate company brochures from websites
- `email_subject_generator.ipynb` - Generate email subject lines
- `query_agent_ollama_openai.ipynb` - Q&A agent using OpenAI or Ollama
- `summarize_website.ipynb` - Website content summarization
- `summarize_local_llm.ipynb` - Summarization using local LLMs
- `technical_assistant_streaming_ollama_openai.ipynb` - Technical assistant with streaming

### Useful UV Commands

- **Add a new dependency**:
  ```bash
  uv add <package-name>
  ```

- **Update dependencies**:
  ```bash
  uv sync
  ```

- **Run any Python command in the UV environment**:
  ```bash
  uv run python <script.py>
  ```

- **Activate the shell** (optional):
  ```bash
  source .venv/bin/activate
  ```

### Troubleshooting

- If you encounter issues with the UV environment, remove and recreate it:
  ```bash
  rm -rf .venv
  uv sync
  ```

- Make sure your `.env` file is properly configured with your API keys
- For Ollama notebooks, ensure the Ollama service is running on `localhost:11434`
