# DevOps Days Labs : Session 2

These are labs overviews to get started with [Azure DevOps Services](https://azure.microsoft.com/en-us/services/devops/).

## Setting up an Azure DevOps environment
In this section, we will configure a new Azure DevOps Service organisation, and setup sample source code used in the next tasks.

If you attended [Lab 1](./devopsdays_lab_session1.md), you can continue on at [Creating a continuous delivery pipeline to automatically deploy changes to Azure](#creatingcipipeline)

1. If you do not already have an account, create a free [Azure account](https://azure.microsoft.com/en-us/free/). We will use this to deploy applications and sites to.

1. If you do not already have a Azure DevOps organisation setup, create a free [Azure DevOps Services](https://go.microsoft.com/fwlink/?LinkId=2014881&campaign=acom~azure~devops~services~main~hero&githubsi=true&clcid=0x409&WebUserId=1C8EEE140888618B2D45E3DF09CC60C9) account.

1. Create a demo application using the demo generator following these [steps](https://www.azuredevopslabs.com/labs/azuredevops/prereq/). <br/>
**`NOTE:`** you are not required to perform "Task 2: Configuring the Parts Unlimited solution in Visual Studio"

  
## <a name="creatingcipipeline" ></a> Creating a continuous delivery pipeline to automatically deploy changes to Azure ##

In this section, we will create a new continuous deploymeny (CD) pipeline that will contniously and automatically deploy changes to Azure by following these [steps](https://www.azuredevopslabs.com/labs/azuredevops/continuousdeployment/).
