# Setting up Splunk enterprize in Docker container

After the docker image has been downloaded we can start the container from the image.

Note that in the run arguments below, we have added a simple password for you.

`docker run -d -p 8000:8000 -p 8088:8088 -e "SPLUNK_START_ARGS=--accept-license" -e "SPLUNK_PASSWORD=123abc456DEF!" --name splunk splunk/splunk:latest`{{execute}}  

The arguments in this command are explained as follows:

* the `-d` is to say that we are launching a detached image
* `-p` specifiys the port in which we want to launch the container which will be 8000, the other -p is the port we will send data to.
* `-e` means that we are setting enviroment variables.
* `"SPLUNK_PASSWORD=<password>"` sets the password for the splunk instance
* `"SPLUNK_START_ARGS=--accept-license"` is necessary for the splunk to be run
* `splunk/splunk:latest` this is the image we downloaded before and the one we want to start

After the command is run it will print out a large hex that is the identifier of the container. 
To make sure that the container is running type  
`docker container ls`{{execute}}  
and look for the status to be healthy.

Unfortunately, kanakoda is restricted in the sense that it does not support simulating individual user tabs, but it does support opening a new one for the new server we just got running from our container.
After the container status is confirmed healthy you can click localhost:8000, the second terminal tab, and you will enter the Splunk enterprise app that we are now running from our container.
You can login to the app with the username `admin` and the `<password>` you set in the previous command.  
  
In the next step we will go through some instructions on how to configure the splunk app in order to be able to send data. 
