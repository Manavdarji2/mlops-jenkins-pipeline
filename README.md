# mlops-jenkins-pipeline

> An automated MLOps CI/CD pipeline for training, serializing, and deploying Machine Learning models using Jenkins and Python.

## Features
- **Automated ML Training:** Executes continuous training loops via centralized Python scripts.
- **Artifact Serialization:** Automatically saves and tracks trained model states using pickle configurations (`model.pkl`).
- **Jenkins Integration:** Fully configured `Jenkinsfile` for orchestrating multi-stage test, build, and deploy cycles.
- **Automated Deployment:** Scripted deployment infrastructure to roll out updated models to target host environments.

## Tech Stack
`Python` · `Jenkins` · `Machine Learning` · `MLOps` · `DevOps`

## Getting Started

### Prerequisites
- Python 3.9+
- A running [Jenkins](https://www.jenkins.io/) server instance with configured Python execution agents.

### Installation
```bash
git clone https://github.com/manav-darji-aiml/mlops-jenkins-pipeline
cd mlops-jenkins-pipeline
pip install -r requirements.txt

```

### Usage

**Running the ML Pipeline Locally:**

```bash
python ml_pipeline.py

```

**Executing the Deployment Script:**

```bash
python deploy.py

```

**Jenkins CI/CD Automation:**

1. Create a new **Pipeline** project within your Jenkins dashboard.
2. Point the Source Code Management (SCM) setting to this repository URL.
3. Jenkins will automatically detect the root `Jenkinsfile` and begin building the multi-stage pipeline.

## Project Structure

```text
mlops-jenkins-pipeline/
├── deploy/             # Core deployment scripts and infrastructure configurations
├── Jenkinsfile         # Jenkins pipeline automation script defining build/deploy stages
├── deploy.py           # Main Python execution script for target environment deployment
├── ml_pipeline.py      # Core data processing, model training, and validation logic
├── model.pkl           # Serialized trained machine learning model artifact
└── requirements.txt    # Python dependencies required to run the pipeline scripts

```

## How It Works

When code modifications or new datasets are committed, the connected Jenkins server triggers a build based on the steps outlined in the `Jenkinsfile`. First, it isolates the environment and installs dependencies from `requirements.txt`. Next, it runs `ml_pipeline.py` to process incoming data and train the model, generating a serialized `model.pkl` file. Finally, `deploy.py` passes the verified artifact through the configurations stored in the `deploy/` directory to push the model into its production hosting framework.

## Contributing

Pull requests welcome. Open an issue first for major changes.

## Author

Manav Darji — [@manav-darji-aiml](https://github.com/manav-darji-aiml)
Topics: python  jenkins  mlops  ci-cd  machine-learning  devops  automation  model-deployment  jenkinsfile

```
