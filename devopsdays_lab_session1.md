# DevOps Days Labs : Session 1

These are labs overviews to get started with [Azure DevOps Services](https://azure.microsoft.com/en-us/services/devops/).

## Setting up an Azure DevOps environment
In this section, we will configure a new Azure DevOps Service organisation, and setup sample source code used in the next tasks.

1. If you do not already have an account, create a free [Azure account](https://azure.microsoft.com/en-us/free/). We will use this to deploy applications and sites to.

1. If you do not already have a Azure DevOps organisation setup, create a free [Azure DevOps Services](https://go.microsoft.com/fwlink/?LinkId=2014881&campaign=acom~azure~devops~services~main~hero&githubsi=true&clcid=0x409&WebUserId=1C8EEE140888618B2D45E3DF09CC60C9) account.

1. Create a demo application using the demo generator following these [steps](https://www.azuredevopslabs.com/labs/azuredevops/prereq/). <br/>
**NOTE** you are not required to perform "Task 2: Configuring the Parts Unlimited solution in Visual Studio"
   
## Setting up a continuous integration build to verify changes and perform tests ##

In this section, we will create a new continuous integration build by following these [steps](https://www.azuredevopslabs.com/labs/azuredevops/continuousintegration/).

## Setting policies to govern changes between repository branches
Now that you have the environment setup and a continuous integration (CI) build. Next we will look at adding some governance to the movement of changes between branches.

### Create a new branch ###

1. Switch to the Azure DevOps browser tab.

1. Navigate to **Repos \| Branches**. Click **New branch**.

    ![](https://github.com/NielZeeman/labs/raw/master/images/devops_1_newbranch.png)

1. Enter a name of **"feature"** for the new branch. Click **Create branch** to create it.

    ![](https://github.com/NielZeeman/labs/raw/master/images/devops_2_featurebranch.png)

1. In the branch list you should see the **"feature"** branch. Select it to navigate to the branch.

### Create a new branch policy ###

1. Select the **"Project settings"**, then scroll down to **"Repos"** and select **"Repositories"**.

1. Expand the **"Git repositories -> PartsUnlimited -. Branches"** and select the **"master"** branch and then **"Policies"**
![](https://github.com/NielZeeman/labs/raw/master/images/devops_3_gitpolicies.png)

1. Check **"Require a minimum number of reviewers"**, enter 1 in **"Minimum number of reviewers"** and also check **"Requestor can approve their own changes"**.<br/>
**NOTE:** Under normal circumstances, you would not allow the requestor to approve their own changes, we will only do this for demo purposes 

1. Click **"Save changes"**.


### Making a local change on a feature branch ###
Now that the branches have been setup and the policies have been configured for your master branch, we are going to make a change in the feature branch and then merge that into the master branch.

1. Select the **"Repos"** view on the left of your Azure DevOps environment. Make sure that you are in the **"feature"** branch and navigate to this file **"PartsUnlimited-aspnet45/src/PartsUnlimitedWebsite/Views/Shared/_Layout.cshtml"**
![](https://github.com/NielZeeman/labs/raw/master/images/devops_4_makechange.png)

1. Click the **"Edit"** button and fine 41 : `<h2>a Fabrikam subsidiary</h2>`. Create a new line below that and add the following `<h2>_name_</h2>`, replacing **"\_name\_"** with your actual name.

1. Click on **"Commit"** and give it a good description, and then click on the **"Commit"** button.

### Creating a pull request to see the changes being merged into master and the builds being kicked off providing the insights into quality ###

1. Now navigate to the **"Repos"** -> **"Pull requests"** view and select **"New pull request"**.
![](https://github.com/NielZeeman/labs/raw/master/images/devops_5_newpullrequest.png)

1. Make sure that you are creating a pullrequest from **"feature"** to **"master"** branches, add yourself as a reviewer, and the **"Create"** the request. 
![](https://github.com/NielZeeman/labs/raw/master/images/devops_6_pullrequest.png)

1. In the next screen, you will see the pull request details. Navigate through and verify the details. Select the **"Files"** tab, hover over the line that was changed and click the "callout" icon on the left. Make a comment on the change.

1. When you are done, click on **"Approve"** button, top right. You will notice that the pull request can now be completed. Click on the **"Complete"** button.

1. On the flyout, uncheck **"Delete feature after merging"** and click **"Complete merge"**.

1. Navigate to the build definition that was configured in the first section, and open it up. Wait for it to complete and then verify that it was successful. Navigate to the **"Tests"** tab and view the test results.

