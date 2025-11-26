# Flask API with CI/CD (GitHub Actions + Vercel)

This project demonstrates a production-ready CI/CD pipeline for a Python Flask API. It includes automated testing via GitHub Actions and continuous deployment.

# 📂 Project Structure

* main.py: The Flask application entry point.
* test_main.py: Unit tests using pytest.
* requirements.txt: Python dependencies.
* vercel.json: Configuration for Vercel Serverless deployment.
* .github/workflows/pipeline.yml: GitHub Actions configuration for CI/CD.

# 🚀 Getting Started

## Prerequisites

* Python 3.9+
* Git

1. Installation

Clone the repository and install dependencies:
```
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name
```

## Create a virtual environment
```
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

## Install requirements
```
pip install -r requirements.txt
```

2. Running Locally

## Standard Python
```
python main.py
```
Access the API at http://localhost:8000.

# 🧪 Running Tests

This project uses pytest for unit testing and flake8 for linting.

To run the full test suite manually:

## Run tests
```
pytest test.py
```

# ⚙️ CI/CD Pipeline

The project is configured with GitHub Actions to automate Integration and Delivery.
## Workflow Overview (pipeline.yml)

Integration Job (CI):
* Triggers on Push or Pull Request to main.
* Sets up Python environment.
* Installs dependencies.
* Runs Linter (flake8) and Tests (pytest).
* If this fails, the deployment job is skipped.

Delivery Job (CD):
* Triggers only on a Push to main (after merge) AND if the Integration job passes.
