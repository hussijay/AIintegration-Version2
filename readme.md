AI-Driven Incident Response Logic App Template
This JSON file is an ARM (Azure Resource Manager) template designed to deploy an AI-integrated Logic App within Azure. 
The Logic App is configured to automate incident response processes in Microsoft Sentinel by leveraging OpenAI's GPT-3.5 model. 
This playbook helps to enhance incident response by automatically generating tasks, comments, and KQL queries based on incident data.

Template Overview
Resource Type: Azure Logic App
Location: East US (eastus)
Identity: System-assigned managed identity for secure connections to Azure Sentinel and OpenAI APIs.
Triggers:
Microsoft Sentinel Incident Creation: The Logic App is triggered whenever a new incident is created in Microsoft Sentinel.
Actions:
GPT-3.5 Tactics and Techniques Description: Generates a detailed description of MITRE ATT&CK tactics related to the incident.
Add Comment to Incident: Posts the generated tactics and techniques description as a comment to the incident.
Generate Tasks for Incident Investigation: Automatically generates tasks to investigate the security incident based on its title, description, and related entities.
Generate KQL Queries: Generates KQL queries to assist in investigating the incident and adds them as tasks to the incident.
Connections:
Azure Sentinel: Secure connection to Microsoft Sentinel to receive incident data and post comments and tasks.
OpenAI API: Secure connection to OpenAI's API to generate incident response recommendations.
Parameters
workflows_ChatGPTIntigrationV2_name: Name of the Logic App workflow (default is ChatGPTIntigrationV2).
connections_MicrosoftSentinel_ChatGPTIntigrationV2_externalid: External ID for the Azure Sentinel connection.
connections_openaiip_2_externalid: External ID for the OpenAI API connection.
How to Use
Deploy the Template
Deploy the Template:

Upload this JSON template to your Azure environment using the Azure Portal, Azure CLI, or PowerShell.
Customize the parameters if necessary to fit your Azure environment.
Configure Connections:

Ensure that the Azure Sentinel and OpenAI API connections are properly configured using managed service identity (MSI).
Trigger the Playbook:

Once deployed, the Logic App will automatically trigger upon incident creation in Microsoft Sentinel, generating and posting AI-driven comments, tasks, and KQL queries.
Use Case
This Logic App is particularly useful for automating the incident response process in a Security Operations Center (SOC). By integrating AI-driven insights directly into the incident management workflow, it helps SOC analysts respond to threats more quickly and efficiently.
To Deploy
	[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/hussijay/AIintegration-Version2/main/template.json)

