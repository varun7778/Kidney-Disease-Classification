# Kidney-Disease-Classification
Technologies Used:
- TensorFlow
- MLflow
- DVC (Data Version Control)
- GitHub Actions
- Docker
- AWS EC2 (Elastic Compute Cloud)
- AWS ECR (Elastic Container Registry)
- AWS IAM (Identity and Access Management)

## Steps to run:

### Clone the repository

```bash
https://github.com/varun7778/Kidney-Disease-Classification.git
```
### Create a conda environment after opening the repository

```bash
conda create -n cicd python=3.8 -y
```

```bash
conda activate cicd
```


### install the requirements
```bash
pip install -r requirements.txt
```

```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```




## MLflow

##### cmd
- mlflow ui

### dagshub
https://dagshub.com/

MLFLOW_TRACKING_URI=https://dagshub.com/varun7778/Kidney-Disease-Classification-MLFlow.mlflow \
MLFLOW_TRACKING_USERNAME=varun7778 \
MLFLOW_TRACKING_PASSWORD=8bbf3dadabd692e64087c2809fba54beaf9aa016 \

Run this to set as env variables:

```bash

set MLFLOW_TRACKING_URI=https://dagshub.com/varun7778/Kidney-Disease-Classification-MLFlow.mlflow

set MLFLOW_TRACKING_USERNAME=varun7778 

set MLFLOW_TRACKING_PASSWORD=8bbf3dadabd692e64087c2809fba54beaf9aa016

```


## DVC cmd
```bash
dvc init
```
```bash
dvc repro
```
```bash
dvc dag
```


## AWS-CICD-Deployment-with-Github-Actions

### 1. Login to AWS console.

### 2. Create IAM user for deployment

	#with specific access to EC2 and ECR.
 
	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
### 3. Create ECR repo to store/save docker image
767398127658.dkr.ecr.us-east-1.amazonaws.com/kidney-project
	
### 4. Create EC2 machine (Ubuntu) 

### 5. Open EC2 and Install docker in EC2 Machine:
	

	sudo apt-get update -y

	sudo apt-get upgrade

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    Github>setting>actions>runner>new self hosted runner> choose os(linux)> then run command one by one in EC2 instance


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME =

