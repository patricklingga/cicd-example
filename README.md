Flask API with CI/CD (GitHub Actions + Vercel)

This project demonstrates a production-ready CI/CD pipeline for a Python Flask API. It includes automated testing via GitHub Actions and continuous deployment to Vercel.

📂 Project Structure

main.py: The Flask application entry point.

test_main.py: Unit tests using pytest.

requirements.txt: Python dependencies.

vercel.json: Configuration for Vercel Serverless deployment.

.github/workflows/pipeline.yml: GitHub Actions configuration for CI/CD.

🚀 Getting Started

Prerequisites

Python 3.9+

Vercel CLI (Optional, for local serverless simulation)

Git

1. Installation

Clone the repository and install dependencies:

git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install requirements
pip install -r requirements.txt


2. Running Locally

Option A: Standard Python (Recommended for logic checks)

python main.py


Access the API at http://localhost:8000.

Option B: Vercel CLI (Recommended for deployment checks)
Simulates the serverless environment locally.

npm i -g vercel
vercel dev


Access the API at http://localhost:3000.

🧪 Running Tests

This project uses pytest for unit testing and flake8 for linting.

To run the full test suite manually:

# Run tests
pytest

# Run linter
flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics


⚙️ CI/CD Pipeline

The project is configured with GitHub Actions to automate Integration and Delivery.

Workflow Overview (pipeline.yml)

Integration Job (CI):

Triggers on Push or Pull Request to main.

Sets up Python environment.

Installs dependencies.

Runs Linter (flake8) and Tests (pytest).

If this fails, the deployment job is skipped.

Delivery Job (CD):

Triggers only on a Push to main (after merge) AND if the Integration job passes.

Uses vercel-cli to build and deploy the application to production.

☁️ Deployment Setup

To enable the automated deployment to Vercel, follow these steps:

Vercel Setup:

Install Vercel CLI: npm i -g vercel

Run vercel link in your project root to link the project to your Vercel account.

This creates a .vercel folder (gitignored). Open .vercel/project.json to find your projectId and orgId.

GitHub Secrets:
Go to your GitHub Repository > Settings > Secrets and variables > Actions and add:

VERCEL_TOKEN: Your personal access token from Vercel Account Settings.

VERCEL_ORG_ID: Found in .vercel/project.json.

VERCEL_PROJECT_ID: Found in .vercel/project.json.

Push to Deploy:
Once configured, any commit pushed to the main branch will automatically trigger the pipeline, run tests, and deploy to Vercel if successful.
