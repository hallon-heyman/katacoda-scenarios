## Searching for data
In this step we are going to explore the splunk search meny. Navigate to the front page of the splunk app by clicking the logo in the top left corner.  
Next in the left columm click the ``Search & Reporting`` to navigate to the search page.  

This page is where splunk is best used, the search page lets you search, show statistics, define patterns and visualize your data. in this tutorial we will only show you how you can search for the data that you sent in the previous step.

In the search bar you can search for "Events", timeranges and much more. The search syntax can be a bit tricky to understand.
Start by searching for the different events you sent.
like `hello world` and if you wrote some other 

To search for all your data you can search for entire indexes by typing `index=main`. This will show all the events because we specified that incomming data to the HEC will be stored in this index but you could ofcourse create different indexes to organise your incomming data.

Another way to search for events is by searching for a specific timerange of the incomming events. this can be done with the keywords `earliest=[+|-]<time>` and `latest=[+|-]<time>` for example `earliest=-1m` will display events from 1 minute ago to the current time, if there were events incomming at this time. 

There is much you can do with splunk and we wont have time to go through all right now. 
## close down
When you are done with this tutorial you want to make sure that you close down the container. This can be done by wrriting `docker container ls` and copying the unique idnetifier for the splunk container. And the executing the command `docker stop <id of container>` and if you want to you can also remove the container with `docker rm <id of container>`