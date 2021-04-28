## Uploading data to splunk
There are many ways to send/uppload data to a splunk instance, you can uppload files of raw data to analyse or  
you can forward logs from your systems to monitor in the interface. In this tutorial we will send test data via curl commands in the terminal to an  
Http Event Collector on splunk (HEC)

### Creating HEC token
In order to send data via HEC we need to create a event collector token on the splunk app. To do this we need to enable HTTP event collector in the setting of the splunk app.
Start by going to your opened instance of splunk at localhost:8000 and navigate to  
 `settings -> Data inputs -> HTTP event collector` in the top navigationbar  
In the top right corner press `Global Settings`
  
In this window you want to make sure that the setting `All tokens` is enabled. 
Also make sure that the HTTP port number corresponds to the same second port in the docker run command (should be port 8088). 
The other options should not be something that you need to worry about due to them being optional. After that is done save the settings.  
  
In the same window click on `New token` next to `Global Settings`.  
Give the token a name of your own choice, and that should be the only setting on this page that you have to set up. click on next in the top.
In the next page go down to index and add all the indexes, next click on review and then submit. The page should then view your created token, save this somewhere until the tutorial is done.  
  
From the same page you can click on the button `Start searching` to navigate to the search page where we will search for our data that we will upload.

### Uploading data
Now we are going to upload data with this curl command. Make sure to attach the token you created at `<HEC Token>` to the command. The `-d` is to signal that we are sending data to splunk the format of the data can be in raw text or JSON format. Try sending this command a bunch of times with different values to the event parameter in the JSON data.

`curl -k "https://localhost:8088/services/collector" -H "Authorization: Splunk <HEC Token>" -d '{"event":"hello world", "sourcetype":"manual"}'`  
In the next step we are going to explore how we can search for these events. 
