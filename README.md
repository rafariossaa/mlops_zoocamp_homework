# Intro

I have started taking [Data Talk Club's  mlops Zoomcamp course](https://github.com/DataTalksClub/mlops-zoomcamp) and this repository will hold files for the corresponding homeworks.

Each subdirectory is for one of the lessons of the course:

## 00 - docker: 

I will hold here docker related files, for example, I have created a base image to use it as development environment.

You would need to create a directory that will be mounted in `/app` and will hold the files used and created inside jupyter.

- Building the image:
```bash
cd 00_docker/base_image
docker build -f Dockerfile -t mlops:v0 .
```

- Running the image:
```bash
mkdir app
chmod -R 777 app
docker run --name jupyter -p 8888:8888 -v ./app:/app mlops:v0
```

## 01 - Intro:
- What is MLOps?
- MLOps maturity model
- NY Taxi dataset (our running example)
- Why MLOps is essential
- Course structure & environment setup

## 02 - Experiment Tracking

The docker image was updated to install mlflow. Build `v2` and run the image with:
```bash
docker run  -it --name jupyter -p 8888:8888 -p 5000:5000 -v ./app:/app mlops:v02
```

- Install MLflow
- Download and preprocess the data
- Train a model with autolog
- Launch the tracking server locally
- Tune model hyperparameters
- Promote the best model to the model registry

