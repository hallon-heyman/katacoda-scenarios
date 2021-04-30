## Searching for data
In this step, we are going to explore the Splunk search interface. Navigate to the front page of the Splunk app by clicking the logo in the top left corner.  
Next in the left column click the ``Search & Reporting`` to navigate to the search page.  

This page is where Splunk is best used, the search page lets you search, show statistics, define patterns and visualize your data. in this tutorial we will only show you how you can search for the data that you sent in the previous step. The beauty of Spunk is for you to explore, and there are many other tutorials and guides out there!

In the search bar, you can search for "Events", time ranges, and much more. The search syntax can be a bit tricky to understand.
Start by searching for the different events you sent.
like `hello world index="history"` and if you wrote some other events.

To search for all your data you can search for entire indexes by typing `index="main"`. This should show all the events because we specified that incoming data to the HEC will be stored in this index but you could of course create different indexes to organize your incoming data. If `index="main"` does not work, try `index="history"`. These are the indexes you added in the previous step!

Another way to search for events is by searching for a specific time range of the incoming events. this can be done with the keywords `earliest=[+|-]<time>` and `latest=[+|-]<time>` for example `earliest=-1m index="history"` will display events from 1 minute ago to the current time in the index history, if there were events incoming at this time. Keep in mind that the longer you wait the higher value on `<time>` is needed. If you set the `<time>` to `-1h` it should encapsulate all the events you sent during this tutorial, you might need to change the index to main to get it to work.  


## close down
When you are done with this tutorial you want to make sure that you close down the container, as is good docker practice. This can be done by writing `docker container ls` and copying the unique identifier for the Splunk container. And then executing the command `docker stop <id of container>` and if you want to you can also remove the container with `docker rm <id of container>`

## Summary

In this tutorial, you have now read and understood docker, and you have used a docker container to start Splunk, and we have sent data to our instance of the Splunk app. Wow, that's quick learning! You can now begin to learn Splunk and analyze any data you want! Enjoy!

