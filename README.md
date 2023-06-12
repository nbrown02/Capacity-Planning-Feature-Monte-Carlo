# Five Minute Capacity Planning for Azure DevOps and Jira

### What is it?
This dashboard is for all those teams and organisations that spend hours in rooms/on virtual meetings, wasting countless hours breaking work down and estimating each individual item to inform their leaders and stakeholders on capacity. Software development is complex yet we continue trying to play tetris when planning capacity. We can do better. This tool uses probabilistic thinking and estimation to provide better forecasts in as lightweight manner as possible, agnostic of whatever way of working the team uses. Inspired by [this video](https://youtu.be/3xX5AzKpV_Q) from [Prateek Singh](https://twitter.com/singhpr), it provides a mechanism for teams to capacity plan in minutes, rather than hours.

### Prerequisites
* [Make sure you have the latest version of Power BI Desktop](https://aka.ms/pbiSingleInstaller)
* Download the appropriate template file:
  - [Azure DevOps / Azure DevOps Server / TFS version](https://github.com/nbrown02/5-Minute-Capacity-Planning/raw/main/5%20Minute%20Capacity%20Planning%20(Azure%20DevOps).pbit)
  - [Jira version](https://github.com/nbrown02/5-Minute-Capacity-Planning/raw/main/5%20Minute%20Capacity%20Planning%20(Jira).pbit) 
* Create/save an access token 
  - [Personal Access Token (PAT) if using Azure DevOps (make sure you have 'Read' Analytics access)](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows)
  - [Jira API token if using Jira](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)
* Then you're good to get started!

### Connectivity (Azure DevOps Version)
* Open the .pbit file in Power BI Desktop
* Select http/https (only choose http if your Azure DevOps Server is HTTP)
* Add the Analytics / Azure DevOps Server URL - for Azure DevOps services enter 'analytics.dev.azure.com' / for Azure DevOps Server enter your server details
* Add your organization and project name

Don't confuse the team name with the project name, a common mistake. If the URL you use is "http://dev.azure.com/Microsoft-UK/AzureDevOpsTeam/Database", then Microsoft-UK is the Organization Name, AzureDevOpsTeam is the Project name, Database is the team name.

* It should then look something like this:

![alt text](https://raw.githubusercontent.com/nbrown02/5-Minute-Capacity-Planning/main/Screenshots/AzDO%20Load.png)

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your PAT you created in the Prerequisites in the password field
  - Leave the username as blank or enter 'Dummy'
  
![alt text](https://docs.microsoft.com/en-us/azure/devops/report/powerbi/media/authentication-7.png?view=azure-devops)

* Once signed in hit 'Load' and wait for your charts to populate!

### Connectivity (Jira Version)
* Open the .pbit file in Power BI Desktop
* Add your Jira URL 
* Add your Jira Project Key 

Don't confuse the project name with the project key, a common mistake! Your project key will be in the URL when viewing an item.

* It should then look something like this:
![alt text](https://raw.githubusercontent.com/nbrown02/5-Minute-Capacity-Planning/main/Screenshots/Jira%20Load.png)

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your email associated with your Jira account for your username
  - Your API token you created in the Prerequisities

![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz-Jira/main/Screenshots/Login2.png)

* Then hit 'Connect' and wait for the data and charts to load!

### How does it work?

![alt text](https://raw.githubusercontent.com/nbrown02/5-Minute-Capacity-Planning/main/Screenshots/Screenshot.png)

### Show me a real example

![alt text](https://raw.githubusercontent.com/nbrown02/5-Minute-Capacity-Planning/main/Screenshots/Screenshot2.png)

- This team has forecast 45 at the 95th percentile for the next 13 weeks
- The 'right-size' for their Features is 8 stories or less (95th percentile)
- 45/8 = 5 (rounded down) - this team has capacity for *5 Features* in the next 13 weeks.
