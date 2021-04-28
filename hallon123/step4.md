## Uploading data to splunk
There are many ways to send/uppload data to a splunk instance, you can uppload files of raw data to analyse or  
you can forward logs from your systems to monitor in the interface. In this tutorial we will send test data via curl commands in the terminal to an  
Http Event Collector on Splunk (HEC)

### Creating HEC token
In order to send data via HEC we need to create a event collector token on the splunk app. To do this we need to enable HTTP event collector in the setting of the Splunk app.
Start by going to your opened instance of splunk at localhost:8000 and navigate to  
 `settings -> Data inputs -> HTTP event collector` in the top navigationbar  
In the top right corner press `Global Settings`
  
In this window you want to make sure that the setting `All tokens` is enabled. 
Also make sure that the HTTP port number corresponds to the same second port in the docker run command (should be port 8088). 
After that is done save the settings.  
  
In the same window click on `New token` next to `Global Settings`.  
Give the token a name of your own choice. Click on next in the top to get to input settings.
In the next page go down to index and add all the indexes by clicking `add all` , next click on review in the top and then submit.
The page should then view your created token and isplay your `Token Value`, save this value anywhere of your choice, or just keep it in your clipboard (ctrl + c).
  
From the same page you can click on the button `Start searching` to navigate to the search page where we will search for our data that we will upload.

### Uploading data
Now we are going to upload data with this curl command back on this katakoda page. Make sure to attach the token you created at `<HEC Token>` to the command. The `-d` is to signal that we are sending data to splunk the format of the data can be in raw text or JSON format. Try sending this command a bunch of times with different values to the event parameter in the JSON data (replace the hello world with different text).

`curl -k "https://localhost:8088/services/collector" -H "Authorization: Splunk <HEC Token>" -d '{"event":"hello world", "sourcetype":"manual"}'`  

So for example `<HEC Token>"` becomes 130d76e6-aa98-4ba9-b2db-fd78cXXXX33". You should receive a 
  `{"text":"Success","code":0}$` if the steps have been correctly followed.
 
In the next step we are going to explore how we can search for these events. 
