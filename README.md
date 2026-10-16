# NeMo Guardrails with OpenAI

A Python project demonstrating how to configure **NVIDIA NeMo Guardrails** with OpenAI models to add input and output safety checks to LLM applications.

## Overview

This project explores how NeMo Guardrails can be used to control LLM interactions through configurable safety checks and custom guardrail flows.

It uses an OpenAI chat model and environment-based configuration to process user queries.

## Features

- Integration with NVIDIA NeMo Guardrails.
- OpenAI model configuration through environment variables.
- Configurable input safety checks.
- Configurable output safety checks.
- Custom guardrail flows using Colang.
- Separation of guardrail configuration and Python application logic.

## Tech Stack

- Python
- NVIDIA NeMo Guardrails
- OpenAI API
- python-dotenv

## Project Structure

```text
project/
├── main.py
├── config.yml
├── config/
│   └── rails.co
├── .env
├── .gitignore
└── README.md
```

## Prerequisites

- Python version compatible with the installed dependencies.
- An OpenAI API key.
- Git.

## Installation

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_PROJECT_FOLDER>
```

### 2. Create and activate a virtual environment

**Windows PowerShell:**

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install nemoguardrails python-dotenv openai
```

## Environment Variables

Create a `.env` file in the project root:

```dotenv
OPENAI_API_KEY=your_openai_api_key
OPENAI_MODEL=gpt-4o-mini
```

Replace the placeholder with your own OpenAI API key.


## Configuration

### `config.yml`

Configures the OpenAI model and the input/output guardrail flows.

### `config/rails.co`

Defines the Colang flows that determine how input and output safety checks are executed and how blocked requests are handled.

### `main.py`

Loads environment variables, initializes the NeMo Guardrails configuration, creates the `LLMRails` instance, and sends a sample user message for processing.

## Run the Application

From the project root, with your virtual environment activated:

```bash
python main.py
```

The application initializes NeMo Guardrails and processes the configured test message using the selected OpenAI model.

## Security Considerations

- Keep API keys in environment variables.
- Test input and output guardrails with both allowed and disallowed prompts.
- Review guardrail behavior to minimize false positives and false negatives.
- Treat LLM-based safety classification as a defense-in-depth measure, not a guarantee of complete protection.

## Future Improvements

- Add PII detection and masking.
- Add automated tests for guardrail behavior.
- Improve error handling and logging.
- Add more specialized guardrail flows.

