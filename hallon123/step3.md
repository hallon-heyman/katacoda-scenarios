## Setting up Splunk enterprize in Docker container

After the docker image has been downloaded we can start the container.
replace <password> with a simple password that contains uppercase and lowercase letters, numbers and special characters like !#  

`docker run -d -p 8000:8000 -p 8088:8088 -e "SPLUNK_START_ARGS=--accept-license" -e "SPLUNK_PASSWORD=123abc456DEF!" --name splunk splunk/splunk:latest`{{execute}}  

we will give an explanation to this command
* the `-d` is to say that we are launching a detached image
* `-p` specifiys the port in which we want to launch the container which will be 8000, the other -p is the port we will send data to.
* `-e` means that we are setting enviroment variables.
* `"SPLUNK_PASSWORD=<password>"` sets the password for the splunk instance
* `"SPLUNK_START_ARGS=--accept-license"` is necessary for the splunk to be run
* `splunk/splunk:latest` this is the image we downloaded before and the one we want to start

after the command is run it will print out a large hex that is the identifier of the container. 
To make sure that the container is running type  
`docker container ls` {{execute}}  
and look for the status to be healty.

After the container status is healty you can open localhost:8000 from the terminal window and you will enter the Splunk enterprise app.
You can login to the app with the username `admin` and the `<password>` you set in the previous command.  
  
In the next step we will go through some instructions on how to configure the splunk app in order to be able to send data. 