# Final Model Deployment
### This folder represents the culmination of research, data exploration, and modeling for the Pharmaceutical Sales Capstone project. These resources are available to view, assess, and recreate the project's findings.

Through extensive data exploration and model evaluation, a final set of (10) features were selected to be used with a Random Forest model. The deployment folder contains scripts to train this model and deploy it to AWS through a Flask REST API and Docker container. The data is preprocessed according to findings discussed previously (for the full documentation please refer to the notebooks in the previous folder), and the model is trained and pickled before deployment.

It is important to note that as of now, the data is pretrained and processed for deployment, meaning that currently, optimizing modeling using a different model or set of features is not possible. However, retraining the used model can be done by using a different set of data. Furthermore, the deployed web application will currently make predictions based on the aformentioned 10 features, but can be further developed to be more flexible in future iterations.

# Viewing and Recreating this project
### Copying this file to your machine
1. Open Git Bash
2. Change current working directory to desired cloned location
3. Clone the repository:
```
git clone https://github.com/kevinjin21/SpringboardProjects/tree/main/Capstone/Pharm_Deploy
```
4. Press enter to create your local clone

For full documentation: https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository

## 1. Training the model
_Skip this step to use the pretrained model.pkl_
<br>Create a new environment or add to an existing environment. Anaconda is recommended but this can be easily done with pip as well. The following instructions will be done using Anaconda, but below is the documentation for setting up a pip environment.
<br> pip: https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/ 

The training script is fairly simple, so only a few dependencies are necessary to run.

```python
conda create -n myenv python=3.10 numpy=1.23.5 pandas=1.5.3 scikit-learn=1.2.1 Flask=2.2.2

# verify that the new environment was installed correctly:
conda env list
```

You should see your new environment in the list of available environments. Once this is done, activate the environment and run the training script. **Note:** Flask is included in the environment for running the application locally (the next step). If you wish to skip this and run the application immediately via Docker, you can remove Flask from the environment setup.

```python
# activate environment
conda activate myenv
python training.py
```

This will create a new pharm_model.pkl file to be used for the deployment model.

## 2. Run the application locally
_Skip this step to move directly to deployment via Docker container_
The model is loaded into a Flask application and is ready to be deployed in a local Docker container. To test the application locally:

1. Follow instructions from Part 1 to setup a python environment
2. Execute the command ```python app.py``` from the terminal
3. The running URLs will be listed (i.e. ```0.0.0.0:80```); visit the URL of choice in your browser to view the web application.
4. To make a prediction, use ```YOUR_URL/predict```, where YOUR_URL is the URL used in step 3.

## 3. Run via Docker 
For instructions on installation and setup of Docker, refer to the following: https://docs.docker.com/desktop/install/windows-install/

Make sure docker is running and installed properly. In your terminal, you can verify the installation using: 
```
docker version
```

We can then build and run the docker image:
```
docker build -t pharm-app .
docker run -p 80:80 pharm-app .
```
(Don't forget the period at the end of the command).

This should build your docker image with the appropriate dependencies and launches the web application. Verify by following steps 3 and 4 from Part 2. Go to the URL http://0.0.0.0:80 for the homepage or http://0.0.0.0:80/predict to make a prediction in your browser (or your URL of choice from listed running URLs).

## 4. (Optional) Deploy to AWS
The final form of this project deployment is hosting it on an EC2 instance on AWS. This requires a bit more setup (and potentially paying for server time), but will be briefly explained here as a further option. The main difference with deploying to AWS is that the URLs can then be accessed from any device, instead of working only locally.

Here is a very simple step-by-step to do so. For a full explanation, please refer to this article: https://towardsdatascience.com/simple-way-to-deploy-machine-learning-models-to-cloud-fd58b771fdcf

1. Make sure you have a properly set-up AWS account and .pem key. This should be saved somewhere privately on your device.
2. Create a new EC2 instance, choosing your desired devices. I have used 't2.micro' for my project. 
3. Before launching the instance, make sure to **change security settings to allow traffic from your desired devices**. For learning purposes, 'All instances' can be used, but should not be used for real applications.
4. Launch the instance. 
5. Sign into the ec2 machine from your local system using the command: 
```
ssh -i /path/my-key-pair.pem ec2-user@public-dns-name
```
Where __/path/my-key-pair.pem__ should lead to your .pem key, and __public-dns-name__ should be your IPv4 DNS link from the AWS console. It should be in the form 'ec2–x–x–x–x.compute-1.amazonaws.com'.
6. Install docker on the EC2 instance using the following commands:
```
sudo yum update -y
sudo yum -y install docker
sudo service docker start
sudo usermod -a -G docker ec2-user
```
7. Log out of the EC2 instance using 'exit' and log back in with Step 5. Check the docker install by using 'docker version' again. Confirm the install and log out.
8. Copy the files: 'requirements.txt', 'app.py', 'pharm_model.pkl', 'Dockerfile' to the ec2 instance using the code:
```
scp -i /path/my-key-pair.pem file-to-copy ec2-user@public-dns-name:/home/ec2-user
```
Using the same __/path/my-kru-pair.pem__ and __public-dns-name__, and adding the four above files in place of __file-to-copy__.

Check to verify the copy of these files by logging back into the EC2 instance using Step 5 and using the 'ls' command.
9. Use the commands from Part 3 (docker build ... and docker run ...) to build your docker container in the EC2 instance.
10. Use the URLs to view the web application!

Again, this is a majorly simplified workflow of deploying the application to AWS. Please refer to the article above for a more in-depth explanation.

## Conclusion
The above steps should allow you to access, test, and deploy the model used in this project. The instructions are written with some assumptions of prior knowledge, and thus may have some confusing areas for newer users! Please feel free to reach out with any questions or feedback on this project! Thank you!