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

 


