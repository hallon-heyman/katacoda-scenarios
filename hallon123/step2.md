## Introduction to Splunk
### Downloading image
Now that we have a introduction to docker and images we can start small by downloading the Splunk enterprise image from the docker hub, to do this execute the following command.  
`docker pull splunk/splunk:latest`{{execute}}  
This might take some time so in the mean time you can read about Splunk down below.

### What is Splunk
Splunk is not open source but you can create a free trial to use Splunk. In this tutorial it is not required of you to create such free account. 
Splunk enterprise which we are using is one of the version that Splunk distributes. It enables you to search, analyse and visualize data that is comming from your components of your IT infrastructure or business. Splunk takes in data from websites, applications, sensors, IOT devices and so on. Splunk indexes theses incomming data streams and translates it to individual events that you can search for.
There is alot you can do with Splunk. you can set up alerts to trigger when special events occur, you can make reports that compile data from searches, identify patterns in your data and much more.   
  
After the previous command is done you can confirm that the image was pulled correctly by typing  
`docker image ls`  
If you see splunk/splunk the command worked correctly. 


