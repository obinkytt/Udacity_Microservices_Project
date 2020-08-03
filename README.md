## Udacity Microservices Project
##### This project tests your ability to operationalize a Python flask app—in a provided file, app.py—that serves out predictions (inference) about housing prices through API calls

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**



## Setup the Environment

### Running `app.py`

#### Standalone:
`app.py` contains the web app built using flask framework.

`python app.py`

#### Run in Docker:  
`run_docker.sh` contains the script to run the app in the docker.

`./run_docker.sh`

#### Run in Kubernetes: 
`run_kubernetes.sh` contains the script to run app in the Kubernetes.

`./run_kubernetes.sh`

### Verify that application is running
`make_prediction.sh` contains the script to check the predictions.

`./make_prediction.sh`

### Upload to Docker Hub
`upload_docker.sh` contains the script to upload the docker image to the Docker Hub.

`./upload_docker.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Kubernetes Clean Up
- `kubectl delete deployment.apps/development`
- `kubectl delete svc development`



##### After serveral attempt to build this project, I decided to use AWS Cloud9 to build a docker image and pushed it to AWS ECR. I used the student starter AWS Console with no cost.

##### I tried using Windows 10 but could not install Docker because HyperV and VMware Compatibility issues. I later tried MacOS Virtual Machine on my Windows 10 Pc. I was stuck on docker build error. I finally decided to use aws Cloud9 which was very easy to use. 




### Cloud9 EC2 Instance and Enviroment
#### Create a new github Repo and connect to Cloud9 with SSH Key. You can now push and pull from Github and AWS Cloud9

![EC2 Inst](https://user-images.githubusercontent.com/4149567/89208938-f587bd80-d582-11ea-8ad5-c2ae43f917ae.jpg)

## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

#### Create a virtualenv and activate it

 * $ python3 -m venv ~/devops
 * $ source ~/devops/bin/activate
 
 #### Run `make install` to install the necessary dependencies: Make install will run the Makefile.
 
 * $ make install
 
### install any dependencies in requirements.txt
 * Flask
 * numpy
 * pandas
 * scikit-learn==0.20.2
 * pylint

### Make Install snapshot
 
 ![makeinstall](https://user-images.githubusercontent.com/4149567/89211539-9d9f8580-d587-11ea-9075-9b88654968df.jpg)
 
#### Run Flask app.py application

  * $ export FLASK_APP=app.py
  * $ flask run

 ## Note:  The Output of App will be run in a browser in a localhost on the EC2 linux instance.
 
 * Serving Flask app "app.py"
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit) 
 * This will not run here. It will run only on localhost
 
 ![app](https://user-images.githubusercontent.com/4149567/89215398-3c2ee500-d58e-11ea-8cf8-149b9657b7f3.jpg)
 
 
 ### Doker Build
 #### We will now build the Docker image
  * $ docker build --tag=app .
  
  ![docbuild](https://user-images.githubusercontent.com/4149567/89215798-e0b12700-d58e-11ea-9010-f601d3acaff4.jpg)
  
 ### Success Docker Build
 
 ![buildsuccesfully](https://user-images.githubusercontent.com/4149567/89215996-3dacdd00-d58f-11ea-963b-8d0c96ae57b4.jpg)
 
 ### List Doker Images
 
   * $ docker image ls
   
## CircleCi and Hadolint
#### I tried to istall CircleCI locally on Cloud9 and I could not make to work. And hadolint did not run. I have to figure it out later because of time constraint to submit this project.

#  Now we will push the image to aws ECR
### Create ECR Environment
#### Connect ECR to Cloud9 and Docker
* $ aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 073492515851.dkr.ecr.us-east-1.amazonaws.com
* $ docker build -t audacity .

##### This will build a new image from Docker to ECR

![ecr build](https://user-images.githubusercontent.com/4149567/89218850-608dc000-d594-11ea-8a7e-ae714e6f1931.jpg)

#### Pushing immage to ECR

$ docker push 073492515851.dkr.ecr.us-east-1.amazonaws.com/audacity:latest

![push ](https://user-images.githubusercontent.com/4149567/89219572-9f704580-d595-11ea-908b-a12b96a2c1b1.jpg)

## You will now find image tag and aws Url on aws ECR console

![pushed image](https://user-images.githubusercontent.com/4149567/89220228-cf6c1880-d596-11ea-9213-c3ebbb6a035c.jpg)




 


