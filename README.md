# Machine Learning Operations (MLOps)

This repository contains practical exercises for the Machine Learning Operations (MLOps) class. It demonstrates various MLOps techniques and best practices for deploying machine learning models.

## Repository Structure

The repository is organized into the following main directories:

### 1. latihan_model_serving_flask
This directory contains examples of serving a machine learning model using Flask:
- `starter/`: Starting code for the exercise
- `solution/`: Complete solution code
- Both contain a model trained on the Fashion MNIST dataset

### 2. latihan_model_serving_tfserving
This directory demonstrates how to serve a model using TensorFlow Serving:
- `starter/`: Starting code for the exercise
- `solution/`: Complete solution code
- Includes a Dockerfile for containerizing the TensorFlow Serving model

### 3. latihan_python_clean_code
This directory focuses on writing clean code for data science and machine learning:
- `starter/`: Contains a notebook for exploratory data analysis
- `solution/`: Contains refactored code with better structure and organization
- Uses the Telco Customer Churn dataset

## Models

The exercises use the following models:
- **Fashion MNIST**: A dataset of 70,000 grayscale images in 10 categories of clothing items
  - Model architecture: Simple neural network with flattening and dense layers
  - Input: 28x28 grayscale images
  - Output: 10 classes (T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle boot)

## Getting Started

### Prerequisites
- Python 3.8+
- TensorFlow 2.8.0
- Flask 2.1.3
- Docker (for TensorFlow Serving)

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd a443-MLOps
```

2. Install the required packages:
```bash
pip install -r requirements.txt
```

### Running the Flask Model Serving

1. Navigate to the Flask serving directory:
```bash
cd latihan_model_serving_flask/solution
```

2. Run the Flask application:
```bash
python main.py
```

3. The model will be available at http://127.0.0.1:5000/predict

### Running TensorFlow Serving with Docker

1. Navigate to the TensorFlow Serving directory:
```bash
cd latihan_model_serving_tfserving/solution
```

2. Build the Docker image:
```bash
docker build -t fashion-mnist-tf-serving .
```

3. Run the Docker container:
```bash
docker run -p 8080:8501 fashion-mnist-tf-serving
```

4. The model will be available at http://localhost:8080/v1/models/fashion-mnist:predict

## Testing the Models

- For both Flask and TensorFlow Serving implementations, you can use the provided `test.ipynb` notebooks to test the deployed models.
- These notebooks include code to send sample Fashion MNIST images to the API endpoints and display predictions.

## Additional Resources

- [TensorFlow Documentation](https://www.tensorflow.org/tfx/guide/serving)
- [Flask Documentation](https://flask.palletsprojects.com/)
- [Docker Documentation](https://docs.docker.com/)

## License

This project is based on code provided by Dicoding as part of their Machine Learning Operations (MLOps) class.