# FBI-Fraud

A final project for DTSC 3602 looking at fraud detection from the FBI using AI/ML techniques for document analysis and fraud detection.

## Features

- **Gemini API Integration**: Uses Google's Generative AI for text analysis
- **OCR Processing**: DeepSeek OCR for document text extraction
- **PDF Analysis**: Automated PDF processing and table extraction
- **Jupyter Notebooks**: Interactive analysis and prototyping

## Prerequisites

- Python 3.9 or higher
- [uv](https://docs.astral.sh/uv/) package manager (10-100x faster than pip)

> **Note**: This project has been migrated from `pip` to `uv` for faster, more reliable dependency management. The `requirements.txt` file is kept for reference only.

## Installation

### 1. Install uv (if not already installed)

```bash
# On macOS and Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# On Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# Or via pip
pip install uv
```

### 2. Clone and setup the project

```bash
git clone <your-repo-url>
cd FBI-Fraud

# Install dependencies (creates .venv automatically)
uv sync

# Optional: Activate virtual environment manually
source .venv/bin/activate  # On macOS/Linux
# or
.venv\Scripts\activate     # On Windows
```

> **Migration from pip**: If you were using `pip install -r requirements.txt`, replace with `uv sync`. All commands now use `uv run` instead of direct execution.

## Usage

### Environment Setup

1. Create a `.env` file in the project root:
```bash
cp .env.example .env
```

2. Add your API keys to `.env`:
```env
GEMINI_API_KEY=your_gemini_api_key_here
```

### Running the Project

#### Jupyter Notebooks
```bash
# Start Jupyter Lab
uv run jupyter lab

# Or start Jupyter Notebook
uv run jupyter notebook
```

#### Python Scripts
```bash
# Run individual scripts
uv run python gemini_test.py
uv run python deepseekOcr.py
uv run python pdfScraping.py
```

### Development

#### Install development dependencies
```bash
uv sync --dev
```

#### Code formatting and linting
```bash
# Format code
uv run black .

# Sort imports
uv run isort .

# Lint code
uv run flake8 .

# Type checking
uv run mypy .
```

## Project Structure

```
FBI-Fraud/
├── .env.example              # Environment variables template
├── .gitignore               # Git ignore rules
├── pyproject.toml           # Project configuration and dependencies
├── uv.lock                  # Locked dependency versions
├── requirements.txt         # Legacy requirements (for reference)
├── README.md               # This file
├── gemini_test.ipynb       # Gemini API testing notebook
├── deepseekOcr.py          # OCR processing script
└── pdfScraping.py          # PDF analysis script
```

## Troubleshooting

### Common Issues

- **"command not found: uv"**: Install uv using the commands above
- **Missing dependencies**: Run `uv sync --reinstall`
- **Add new dependencies**: `uv add package-name` or `uv add --dev package-name`
- **Remove dependencies**: `uv remove package-name`

### Jupyter Kernel

The project includes a registered Jupyter kernel "FBI-Fraud (uv)" that uses the uv environment. Start Jupyter with `uv run jupyter lab` and select this kernel for all notebooks.

## Dependencies

### Core Dependencies
- `google-generativeai`: Google's Generative AI API
- `python-dotenv`: Environment variable management

### Data Processing
- `pandas`: Data manipulation and analysis
- `beautifulsoup4`: HTML/XML parsing
- `pypdf`: PDF processing
- `pdfplumber`: Advanced PDF text extraction

### ML/AI
- `transformers`: Hugging Face transformers
- `torch`: PyTorch for deep learning
- `vllm`: High-performance LLM inference
- `Pillow`: Image processing

### Development
- `jupyter`: Jupyter notebook environment
- `ipykernel`: Jupyter kernel
- `ipywidgets`: Interactive widgets
- `tqdm`: Progress bars

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Run tests and linting: `uv run pytest` and `uv run flake8`
5. Commit your changes: `git commit -m "Add feature"`
6. Push to the branch: `git push origin feature-name`
7. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
