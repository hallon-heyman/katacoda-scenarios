# Setting up Splunk enterprize in Docker container

After the docker image has been downloaded we can start the container from the image. It might take a minute or two for Docker to pull and extract Splunk depending on your setup.

`docker run -d -p 8000:8000 -p 8088:8088 -e "SPLUNK_START_ARGS=--accept-license" -e "SPLUNK_PASSWORD=3aSteR3GG!" --name splunk splunk/splunk:latest`{{execute}}  

The arguments in this command are explained as follows:
* the `-d` is to say that we are launching a detached image
* `-p` specifies what port we want to open for the communication between the host and the container, in this command we provide 2 `-p` flags the other one is the port we will use to set up our HTTP Event Collector in the next step.
* `-e` means that we are setting enviroment variables.
* `"SPLUNK_PASSWORD=<password>"` sets the password for the Splunk instance.
* `"SPLUNK_START_ARGS=--accept-license"` is necessary for the Splunk to be run.
* `--name` gives our container the name Splunk.
* `splunk/splunk:latest` this is the image we downloaded before and the one we want to start

After the command is run it will print out a large hex that is the identifier of the container. 
To make sure that the container is running type  
`docker container ls`{{execute}}  
and look for the status to be healthy, if it says health:starting you must wait until it only says "(healthy), this can take a few minutes. You can inspect the the Splunk container using the inspect command from the previous step while you do this to repeat what you have learned!


Unfortunately, kanakoda is restricted in the sense that it does not support simulating individual user tabs, but it does support opening a new one for the new server we just got running from our container.
After the container status is confirmed healthy as per above, you can click port 8000, the second terminal tab, and you will enter the Splunk enterprise app that we are now running from our container.
You can login to the app with the username `admin` and the `<password>` you set in the previous command. 
  
When you have logged in you can go onto the next step we will go through some instructions on how to configure the splunk app in order to be able to send data. 
