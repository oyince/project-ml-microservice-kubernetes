[![oyince](https://circleci.com/gh/oyince/project-ml-microservice-kubernetes.svg?style=svg)](https://app.circleci.com/pipelines/github/oyince/project-ml-microservice-kubernetes)

# Project Overview
This project contains a Machine Learning Microservice built on skLearn. The `sklearn` model has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on.  The data was taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing) and can be of informational value.

### What does this project do?
Run a docker container

Upload container into hub.docker.com

Run the deployed application in a Kubernetes cluster

Integrate with CircleCI for continuous integration

### The process

Step 1:

Fork this repo and clone it to your local workstation

	- git clone https://github.com/oyince/project-ml-microservice-kubernetes.git


Step 2:

Navigate to the directory

	- cd project-ml-microservice-kubernetes

Step 3:

Setup the virtual environment, in my case since I used an EC2 instance running ubuntu, I had to update packages, then upgrade python 3.
	
    - python3 -m venv ~/.devops
	
    - source ~/.devops/bin/activate

Installed the dependecies by running "Makefile"

Installed docker, Hadolint and kubernetes

Step 4:

Fixed the docker.sh file - added working directory, exposed port 80, added the run "app.py" command 

Run the docker application "./run_docker.sh"

Step 5:

Fixed the upload_docker.sh file - created dockerpath and personalized the docker name

Run ./upload_docker.sh to uplaod to docker hub

Step 6:

Included the command to run the dockerhub container with kubernetes and port forwarding

run kubernetes ./run_kubernetes.sh

Step 7: 

Run prediction ./make_prediction.sh

Step 8:

Create a .cirleci directory and a config.yml file, for confirmation that the project works.

### Requirement
Python3.7
