# mc-intro-mlops
Masterclass intro MLOPS with zenml

```sh
# clone the ZenML repository
git clone https://github.com/zenml-io/zenml.git
cd zenml/examples/quickstart

# create a virtual env
python3 -m venv zenmlenv

# Install ZenML
pip install "zenml[server]"

# Install required zenml integrations
zenml integration install sklearn -y

# Initialize ZenML
zenml init

# Start the ZenServer to enable dashboard access
zenml up

# open http://127.0.0.1:8237/. Log in with the default username "default" (password not required).

# Run the feature engineering pipeline
python run.py --feature-pipeline

# Run the training pipeline
python run.py --training-pipeline

# Run the training pipeline with versioned artifacts
python run.py --training-pipeline --train-dataset-version-name=1 --test-dataset-version-name=1

# Run the inference pipeline
python run.py --inference-pipeline
```