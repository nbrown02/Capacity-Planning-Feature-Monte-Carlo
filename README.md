# Five Minute Capacity Planning for Azure DevOps and Jira

### What is it?
This dashboard is for all those teams and organisations that spend hours in rooms/on virtual meetings, wasting countless hours breaking work down and estimating each individual item to inform their leaders and stakeholders on capacity. Software development is complex yet we continue trying to play tetris when planning capacity. We can do better. This tool uses probabilistic thinking and estimation to provide better forecasts in as lightweight manner as possible, agnostic of whatever way of working the team uses. Inspired by [this video](https://youtu.be/3xX5AzKpV_Q) from [Prateek Singh](https://twitter.com/singhpr), it provides a mechanism for teams to capacity plan in minutes, rather than hours.

### Prerequisites
* [Make sure you have the latest version of Power BI Desktop](https://aka.ms/pbiSingleInstaller)
* Download the appropriate template file:
  - [Azure DevOps / Azure DevOps Server / TFS version](https://github.com/nbrown02/FlowViz/raw/main/FlowViz%20(Project).pbit)
  - [Jira version](https://github.com/nbrown02/FlowViz/raw/main/FlowViz%20(Organization).pbit) 
* Then you're good to get started!

### Connectivity (Azure DevOps Version)
* Open the .pbit file in Power BI Desktop
* Select http/https (only choose http if your Azure DevOps Server is HTTP)
* Add the Analytics / Azure DevOps Server URL - for Azure DevOps services enter 'analytics.dev.azure.com' / for Azure DevOps Server enter your server details
* Add your organization and project name

Don't confuse the team name with the project name, a common mistake. If the URL you use is "http://dev.azure.com/Microsoft-UK/AzureDevOpsTeam/Database", then Microsoft-UK is the Organization Name, AzureDevOpsTeam is the Project name, Database is the team name.

* It should then look something like this:

![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz/main/Screenshots/AzDO%20Services%20Login.png)

* Hit 'Load' 
* If you are prompted for a login, you can choose:
  - 'Organizational' and enter your Organization email/password (if required) and sign in
  - 'Basic' and use a Personal Access Token (PAT) to login, entering it in the password field (user can be left as blank - make sure it has 'Read' access to Analytics)

  ![alt text](https://docs.microsoft.com/en-us/azure/devops/report/powerbi/media/authentication-7.png?view=azure-devops)

* Once signed in hit 'Load' and wait for your charts to populate!

### Connectivity (Jira Version)
* Open the .pbit file in Power BI Desktop
* Add your Jira URL 
* Add your Jira Project Key 

Don't confuse the project name with the project key, a common mistake! Your project key will be in the URL when viewing an item.

* It should then look something like this:
![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz-Jira/main/Screenshots/Login1.png)

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your email associated with your Jira account for your username
  - Your API token you created in the Prerequisities

![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz-Jira/main/Screenshots/Login2.png)

* Then hit 'Connect' and wait for the data and charts to load!

### How does it work?
xxxxx
