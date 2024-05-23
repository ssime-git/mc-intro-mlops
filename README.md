# mc-intro-mlops

## ZenML presentation :

### What is ZenML?

ZenML is an extensible, open-source MLOps framework designed to create reproducible and production-ready machine learning pipelines. It focuses on simplifying the creation, deployment, and management of ML workflows. ZenML abstracts away the complexity of integrating various ML tools and platforms, providing a seamless experience for data scientists and ML engineers.

### Key Capabilities of ZenML

1. **Pipeline Creation**: ZenML allows users to define their ML workflows as code, making it easy to create, visualize, and manage complex pipelines.
2. **Reproducibility**: Ensures that pipelines are reproducible, enabling consistent results across different runs and environments.
3. **Extensibility**: ZenML integrates with various ML tools and platforms, allowing users to plug in their preferred tools for data processing, model training, and deployment.
4. **Version Control**: Tracks changes to pipelines, enabling users to version control their experiments and models.
5. **Deployment**: Facilitates the deployment of ML models into production with built-in support for various deployment targets.
6. **Monitoring and Logging**: Provides tools for monitoring and logging the performance of models in production.

### Comparison with Apache Airflow

1. **Purpose**:
   - **ZenML**: Specifically designed for MLOps, focusing on ML pipeline creation, management, and deployment.
   - **Apache Airflow**: A general-purpose workflow orchestration tool that can be used for a wide range of workflows, including but not limited to ML.

2. **Ease of Use**:
   - **ZenML**: Easier to use for ML-specific tasks due to its specialized features and abstractions tailored for ML workflows.
   - **Apache Airflow**: Requires more configuration and setup, making it more flexible but also more complex for ML tasks.

3. **Reproducibility**:
   - **ZenML**: Emphasizes reproducibility by design, ensuring consistent results across different environments and runs.
   - **Apache Airflow**: While it can support reproducibility, it requires more manual effort to ensure consistent environments and results.

4. **Integration with ML Tools**:
   - **ZenML**: Integrates seamlessly with various ML tools and platforms, making it easy to switch and combine different tools within the same pipeline.
   - **Apache Airflow**: Provides flexibility to integrate with a wide range of tools, but integrations for ML-specific tools might need custom development.

5. **Deployment and Monitoring**:
   - **ZenML**: Built-in support for deploying ML models and monitoring their performance in production.
   - **Apache Airflow**: Can be used for deployment and monitoring, but it requires more setup and configuration to achieve the same level of functionality as ZenML.

### Summary

ZenML is a user-friendly MLOps framework that simplifies the process of creating, managing, and deploying machine learning pipelines. It is designed to be easy to use for data scientists and ML engineers, with built-in features that ensure reproducibility and integration with various ML tools. In contrast, Apache Airflow is a more general-purpose workflow orchestration tool that provides greater flexibility but requires more manual setup for ML tasks.

For beginners, ZenML offers a more straightforward and streamlined approach to managing ML workflows, making it an excellent choice for those starting in the field of MLOps.

#### Key Capabilities of ZenML

1. **Pipeline Creation**: Define ML workflows as code, making it easy to create, visualize, and manage complex pipelines.
2. **Reproducibility**: Ensure consistent results across different runs and environments.
3. **Extensibility**: Integrate with various ML tools and platforms.
4. **Version Control**: Track changes to pipelines and experiments.
5. **Deployment**: Facilitate the deployment of ML models into production.
6. **Monitoring and Logging**: Tools for monitoring and logging model performance in production.

#### Comparison with Apache Airflow summary

| Feature               | ZenML                                      | Apache Airflow                          |
|-----------------------|--------------------------------------------|-----------------------------------------|
| **Purpose**           | MLOps framework for ML pipelines           | General-purpose workflow orchestration  |
| **Ease of Use**       | User-friendly for ML tasks                 | Flexible but requires more configuration|
| **Reproducibility**   | Ensures reproducibility by design          | Requires manual effort for consistency  |
| **ML Tool Integration** | Seamless integration with ML tools       | Custom development needed for ML tools  |
| **Deployment**        | Built-in support for model deployment      | Requires setup for deployment tasks     |
| **Monitoring**        | Built-in monitoring tools                  | Requires configuration for monitoring   |


## Practice with zenML

The best way to learn zenML is by of course using it practically speaking, so let's dive in :


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