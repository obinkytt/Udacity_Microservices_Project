## Udacity Microservices Project
##### This project tests your ability to operationalize a Python flask app—in a provided file, app.py—that serves out predictions (inference) about housing prices through API calls

##### After serveral attempt to build this project, I decided to use AWS Cloud9 to build a docker image and pushed it to AWS ECR. I used the student starter AWS Console with no cost.

##### I tried using Windows 10 but could not install Docker because HyperV and VMware Compatibility issues. I later tried MacOS Virtual Machine on my Windows 10 Pc. I was stuck on docker build error. I finally decided to use aws Cloud9 which was very easy to use. 

### Cloud9 EC2 Instance and Enviroment

![EC2 Inst](https://user-images.githubusercontent.com/4149567/89208938-f587bd80-d582-11ea-8ad5-c2ae43f917ae.jpg)


## Setup the Environment

#### Create a virtualenv and activate it

 * $ python3 -m venv ~/devops
 * $ source ~/devops/bin/activate
 
 #### Run `make install` to install the necessary dependencies
