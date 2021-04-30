## Searching for data
In this step we are going to explore the splunk search meny. Navigate to the front page of the splunk app by clicking the logo in the top left corner.  
Next in the left columm click the ``Search & Reporting`` to navigate to the search page.  

This page is where splunk is best used, the search page lets you search, show statistics, define patterns and visualize your data. in this tutorial we will only show you how you can search for the data that you sent in the previous step. The beauty of Spunk is for you to explore, and there are many other tutorials and guides out there!

In the search bar you can search for "Events", timeranges and much more. The search syntax can be a bit tricky to understand.
Start by searching for the different events you sent.
like `hello world` and if you wrote some other .

To search for all your data you can search for entire indexes by typing `index="main"`. This should show all the events because we specified that incomming data to the HEC will be stored in this index but you could ofcourse create different indexes to organise your incoming data. If `index="main"` does not work, try `index ="history"`. These are the indexes you added in the previous step!

Another way to search for events is by searching for a specific timerange of the incomming events. this can be done with the keywords `earliest=[+|-]<time>` and `latest=[+|-]<time>` for example `earliest=-1m` will display events from 1 minute ago to the current time, if there were events incomming at this time. Keep in mind that the longer you wait the higher value on `<time>` is needed. If you set the `<time>` to `-1h` it should encapsulate all the event you sent during this tutorial.  

## close down
When you are done with this tutorial you want to make sure that you close down the container, as is good docker practice. This can be done by wrriting `docker container ls` and copying the unique idnetifier for the splunk container. And the executing the command `docker stop <id of container>` and if you want to you can also remove the container with `docker rm <id of container>`

## Summary

In this tutorial you have now read and understood docker, and you have used a docker container to start splunk, and we have sent data to our own instance of the splunk app. Wew, that's quick learning! You can know begin to learn splunk and analyse any data you want! Enjoy!

