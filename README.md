# github-jira-issue-automation
Automatically fetches the issues created in GitHub and creates these issues/tickets in Jira for easier tracking.

Follow the steps below:
1. Create an API token in Jira. Pass your Email ID and API Token in the auth section of list-projects.py. Modify the code to use env variables for the API Token if needed.
2. For the Issue-Type ID to be updated in the create-jira.py, navigate to the project and click on Configure Board in the top-right dropdown and navigate to the issue type (Epic, Story, Task, Bug) on the left side. Select the Issue-ID from the URL (last URL parameter). Also, update the project-key (project alphabetic identifier) in the same file.
3. Create a flask application. Copy the list-projects.py code into the flask function and make sure that the indentation is right.
4. Create an EC2 instance and copy the flask-app.py file to the instance. Make sure to install Python, PIP and Flask in the EC2 instance. Ensure to allow inbound connections over port 5000. Now run the server.
5. Go to Github repo and and create a webhook. Add the EC2 instance link in the Webhook and select the individual event (Issue Comments, Pushes).
6. The code can be modified to ensure that the issue is created only based on certain comments (For example: /jira). This will create issues in Jira only when the keyword is used - this can mean that developer has accepted the issue with a particular keyword in GitHub issue discussion and Jira issue will automatically be created.