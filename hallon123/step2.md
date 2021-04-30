## Introduction to Splunk
### Downloading image
Now that we have an introduction to docker and images we can start small by downloading the Splunk enterprise image from the docker hub, to do this execute the following command.  
`docker pull splunk/splunk:latest`{{execute}}. As you now know, this fetches the latest version of the official Splunk image from the Docker Hub registry. 
This might take some time so in the meantime, you can read about Splunk down below, or read this [gem](https://www.guru99.com/splunk-tutorial.html#1) of an introduction by Guru99!

### What is Splunk
Splunk is not open source but you can create a free trial to use Splunk. In this tutorial, it is not required of you to create a free account. 
Splunk enterprise which we are using is one of the versions that Splunk distributes. It enables you to search, analyze and visualize data that is coming from the components of your IT infrastructure or business. Splunk takes in data from websites, applications, sensors, IoT devices, and so on. Splunk indexes these incoming data streams and translates them to individual events that you can search for.
There is a lot you can do with Splunk. you can set up alerts to trigger when special events occur, you can make reports that compile data from searches, identify patterns in your data, and much more.  
  
After the previous command is done you can confirm that the image was pulled correctly by typing  
`docker image ls`  
If you see splunk/splunk the command worked correctly. 


