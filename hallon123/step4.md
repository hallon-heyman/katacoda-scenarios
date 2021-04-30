## Uploading data to Splunk
There are many ways to send/upload data to a Splunk instance, you can upload files of raw data to analyze or you can forward logs from your systems to monitor in the interface. In this tutorial, we will send test data via curl commands in the terminal to an  
HTTP Event Collector on Splunk (HEC). An HTTP Event Collector lets you send data and application events to your Splunk app over the HTTP (HTTPS) protocol.
### Splunk events
An event in splunk refers to any individual piece of data. The custom data that is sent to the Splunk app are called Splunk Events. This data can be in any format, for example a string, a number or a JSON object. In Splunk you can create custom event type that help you categories the incoming based on common characteristics.

### Creating HEC token
To send data via HEC we need to create an event collector token in the Splunk app. To do this we need to enable HTTP event collector in the setting of the Splunk app.
Start by going to your opened instance of Splunk at localhost:8000 and navigate to  
 `settings -> Data inputs -> HTTP event collector` in the top navigation bar  
In the top right corner press `Global Settings`
  
In this window, you want to make sure that the setting `All tokens` is enabled. 
Also, make sure that the HTTP port number corresponds to the same second port in the docker run command (should be port 8088). 
After that is done save the settings. Now we have made sure that the Splunk app can receive events via HTTP, no we need to create a token for authorization
  
In the same window click on `New token` next to `Global Settings`.  
Give the token a name of your own choice. Click on next at the top to get to input settings.
On the next page go down to index and add all the indexes by clicking `add all`, next click on review at the top, and then submit.
The page should then view your created token and display your `Token Value`, save this value anywhere of your choice, or just keep it in your clipboard (ctrl + c).
  
From the same page, you can click on the button `Start searching` to navigate to the search page where we will search for the data that we will upload.

### Uploading data
Now we are going to upload data with this curl command back on this Katakoda page. Make sure to attach the token you created at `<HEC Token>` to the command. The `-d` is to signal that we are sending data to Splunk the format of the data can be in raw text or JSON format. Try sending this command a bunch of times with different values to the event parameter in the JSON data (replace the hello world with different text).

`curl -k "https://localhost:8088/services/collector" -H "Authorization: Splunk <HEC Token>" -d '{"event":"hello world", "sourcetype":"manual"}'`  

So for example `<HEC Token>"` becomes 130d76e6-aa98-4ba9-b2db-fd78cXXXX33". You should receive a 
  `{"text":"Success","code":0}$` if the steps have been correctly followed.
 
In the next step, we are going to explore how we can search for these events. 
