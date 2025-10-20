# Capacity Planning & Feature Monte Carlo for Azure DevOps and Jira (Cloud)

### What is this report? 
This will the likely completion date of Features in your backlog right now based on the number of child items and a forecasted target date, detail the ‘rightsize’ for your Features as well as the number of these Features you have capacity for in a given time period . Please note, when I say Features, I mean the backlog hierarchy level above User Story/Product Backlog Item. The respective templates use the appropriate terminology (e.g. Jira uses Epic, ADO uses Feature).

### Why would you use it? 
- Use it to improve your confidence around delivery dates for Features/Epics, as well as modelling 'what if' scenarios. 
- Better understand how ‘big’ (in terms of child items) your Features/Epics are
- Understand how many Features/Epics you have capacity for in a given time period (e.g. a quarter/quarterly planning)

### When would you use it?
- You can use the Epic/Feature Monte Carlo as often as you need to (at a minimum I'd say weekly) to understand forecasted delivery dates vs. expectations
- You can use the rightsizing page on a frequent basis (e.g. weekly) for monitoring Feature/Epic size.
- Capacity Planning could be used in the build-up to quarterly planning (or similar type of event if you have it) to understand team capacity

### Prerequisites
* Your team needs to have the following practices in place:
  - Your team regularly review and move work items (User Stories, PBIs, Features, Epics, etc.) to in progress (when started) and done (once complete)
  - Your team regularly monitor the size (in terms of number of child work items) of Features/Epics
  - At all levels you always try to break work down to thin, vertical slices
  - Features/Epics are 'owned' by a single team (i.e. not shared across multiple teams)
* Download the appropriate template file:
  - [Azure DevOps / Azure DevOps Server / TFS version](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/raw/main/Capacity%20Planning%20&%20Feature%20Monte%20Carlo%20(ADO).pbit)
  - [Jira version](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/raw/main/Capacity%20Planning%20&%20Feature%20Monte%20Carlo%20(Jira).pbit) 
* Create/save an access token 
  - [Personal Access Token (PAT) if using Azure DevOps (make sure you have 'Read' Analytics access)](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows)
  - [Jira API token if using Jira](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)
* Then you're good to get started!

### Connectivity (Azure DevOps Version)
* Open the .pbit file in Power BI Desktop
* Select http/https (only choose http if your Azure DevOps Server is HTTP)
* Add the Analytics / Azure DevOps Server URL - for Azure DevOps services enter 'analytics.dev.azure.com' / for Azure DevOps Server enter your server details
* Add your organization, project name and team name, as well as the projects where the respective work items (Stories/Features/Epics) live. This may be the same project for all of them, or you may use different projects for 'portfolio' views.

Don't confuse the team name with the project name, a common mistake. If the URL you use is "http://dev.azure.com/Microsoft-UK/AzureDevOpsTeam/Database", then Microsoft-UK is the Organization Name, AzureDevOpsTeam is the Project name, Database is the team name.

* It should then look something like this:

<img width="650" height="600" alt="image" src="https://github.com/user-attachments/assets/77dc6148-5487-4f43-be3f-46c61edfdef7" />

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your PAT you created in the Prerequisites in the password field
  - Leave the username as blank or enter 'Dummy'
  
![alt text](https://docs.microsoft.com/en-us/azure/devops/report/powerbi/media/authentication-7.png?view=azure-devops)

* Once signed in hit 'Load' and wait for your charts to populate!


### Connectivity (Jira Version)
* Open the .pbit file in Power BI Desktop
* Add your Jira URL 
* Add your Jira Project Keys for where Stories and Epics live, this may be the same project (if so just copy/paste) or different

Don't confuse the project name with the project key, a common mistake! Your project key will be in the URL when viewing an item.

* Add the custom field value for the rank field - to figure this out go to the jira search in your respective instance and start to type 'Rank' into the search, as you type it will reveal the custom field ID:

  <img width="400" height="150" alt="image" src="https://github.com/user-attachments/assets/a32a7fc2-71be-4c92-92e0-ea375a39d7d9" />

  Therefore I would enter customfield_10019
  
* It should then look something like this:

<img width="650" height="600" alt="image" src="https://github.com/user-attachments/assets/3b88edb7-f4d5-4e0e-860e-6acd571b363c" />

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your email associated with your Jira account for your username
  - Your API token you created in the Prerequisities

![alt text](https://raw.githubusercontent.com/nbrown02/FlowViz-Jira/main/Screenshots/Login2.png)

* Then hit 'Connect' and wait for the data and charts to load!

## Using the report
There are a few different ways you can use each chart.

### Feature Monte Carlo
There are two main ways to use this report:

Better understand/manage expectations on delivery - by using this report you are able to define a target date and percentage likelihood outcome to aim for. You can play around with the drop down options for these two fields to see the different outcomes that could occur and how likely (or unlikely!) an outcome for a particular Feature is.

<img width="1614" height="871" alt="image" src="https://github.com/user-attachments/assets/72521f61-96ec-4455-8a48-fa1bb5b71623" />

Understand the impact WIP has on delivery - the problem with forecasting at Feature level is that it typically assumes one feature is worked on sequentially in priority order by a team, which is simply not the reality we face. It is underestimated just how much of an impact Feature WIP has on teams. Even if a team is limiting WIP at story level, this is redundant for Feature throughput if WIP is not limited at the level above that.

### Feature Rightsizing

![image-20230922-111614](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/9031b0aa-3d5f-46a2-ac14-a52c486b608c)

Using this chart we can see that the “right size” for our Features is 7 child items (User Stories/PBIs) or less. We should therefore try to ensure the majority of our Features are no bigger than this. The table to the right highlights any ‘open’ Features that are under/at/exceed our rightsize. You’d use this to focus on those that are “too big” and potentially be trying to find ways to break them down.

### Feature Capacity Planning

![image-20230926-092436](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/5acbc3f2-a0ed-4881-b7b5-8a7f97c8ae5e)

Using this chart we can see that we are forecasting this team have an 85% likelihood of completing 96 stories or more in the next 12 weeks. We can also see that 85% of our Features have 7 child items or less. When we divide 96 by 7 we get 13.71 - seen as we can’t have .71 of a Feature we round down therefore we can say that in the next 12 weeks, this team has capacity for 13 rightsized Features.

One of the advantages of this approach is the ability to see the likelihood of different outcomes that could occur and how reasonable (or unreasonable!) expectations may be around capacity. Use the dropdown to play around with the different percentile likelihoods depending on your risk appetite:

![FCRESULTS3 (1)](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/2f5ccfab-3edb-4a43-b707-408fdbe7e387)

### Know limitations/common questions
- The Jira version only works at project level, if you have multiple teams in a project you will need to modify this using the field you use to differentiate a team with
- The ADO version is team level only as, due to the monte carlo simulations, doing it at a project level would likely mean the report would not load (due to the amount of rows needed)
- A Process Behaviour Chart is included in the What Will We Get? help tooltip, which indicates how predictable your input data (Throughput) is
![Screenshot (125)](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/assets/29369962/a093477d-859b-4839-bfd0-faf0a3483b46)
