## Setting up Splunk enterprize in Docker container

`Docker login` {{execute}}

Next we will download the container image from the docker hub  

`docker pull splunk/splunk` {{execute}}

After the docker image has been downloaded we can start the container.
replace <password> with a simple password that contains uppercase and lowercase letters, numbers and special characters like !#  

`docker run -d -p 8000:8000 -e "SPLUNK_START_ARGS=--accept-license" -e "SPLUNK_PASSWORD=<password>" --name splunk splunk/splunk:latest` {{execute}}  

we will give an explanation to this command
* the -d is to say that we are launching a detached image
* -p specifiys the port in which we want to launch the container
* -e means that we are setting enviroment variables.
* "SPLUNK_PASSWORD=<password>" sets the password for the splunk instance
* "SPLUNK_START_ARGS=--accept-license" is necessary for the splunk to be run
* splunk/splunk:latest this is the image we downloaded before and the one we want to start

after the command is run it will print out a large hex that is the identifier of the container. 
To make sure that the container is running type  
`docker container ls` {{execute}}  
and look for the status to be healty.