# Intro to UrbanCode Deploy Workshop
## Prerequisites for this workshop
* UrbanCode Deploy is installed on a system.
* Agent installed and connected and online for the UrbanCode Deploy server.
* The following plugins installed  **TODO** 
* Download and unzip the following file:
	* 	https://.....  **TODO**
*  Create target deployment directories.  Make two directories: 
	* C:\TEMP\DEV and 
	* C:\TEMP\TEST
* Create a Top-Level group in Resources.
	* Click on "Resources" in the top row of tabs.
	* Click on "Create Top-Level Group"
		* Name: Hello-World
		* Click Save.
	* Hover your mouse on this new line (the line with Hello-World).  
		* When "Actions" appears, click on this and select "Add group".
		* Name: DEV
		* Click Save.
	* Hover your mouse on the Hello-World line again.
		* When "Actions" appears, click on this and select "Add group".
		* Name: TEST
		* Click Save.

# Overview
--- 
UrbanCode Deploy maintains an Application centric view of its world.  An application is comprised of one or more components and environments (places where the application/components are deployed).  To start our exercise, we will begin by creating a component. 

# Lab 1
--- 
## Components
**TODO**  Define a component.

### Create a component
* Click on top level "Components" tab.
* Click on "Create Component" button.
* Name: hello-world-html
* Source Configuration Type: File System
* Base Path: C:\Home\<user>\UCD\hello-world-html
* Click "Save".

### Create a component version
* Find "hello-world-html" in the component list and click on it.
* Navigate to the directory where you downloaded and unzipped the archive.
* Examine the file "index.html"
* In the UCD web interface, navigate "Components" then select "hello-world-html".
* In the second row of tabs, click on Versions.
* Click on "Import New Version".
* Provide and Name for the version (required) and a description (option).
* Click "Save".
* Click "Refresh" at the bottom of the page.
 

### Create a component process
* In the second row of tabs, click on "Processes".
* Click on "Create Process"
* Name: deploy-web-page
* Click on "Save".
* Note the process is now listed in the table.
* Click on "deploy-web-page".
* Add your first step to the process.
	* Click in the filter above the list of steps.
	* Type "Delete files".  
	* Drag and drop the step "Delete Files and Directories" on to the canvas.
	* Click on the pencil icon to edit the details of the step.
		* You may change the name if you desire.
		* Verify that there is a period "." in the Base Directory field.
		* Click in the editor box for Include.  Enter \*\*/\* in this box.
		* Click Save to save the file specification for the Include field.
		* Click Save to save the details for this step.
		
* Add a second step.
	* Use the filter again and search for "Download".
	* Drag and drop "Download Artifacts" and drop it onto the line between the first step and Finish.  When the line turns blue, you are in the correct location to drop the step.
	* **TODO**: Follow these steps if your process does not look like the following: **IMAGE**
	* Click on the pencil icon to edit the details of the step.
		* You may change the name if you desire.
		* Verify that there is a period "." in the Base Directory field.
		* Click in the editor box for Include. Enter \*\*/\* in this box.
		* Click Save to save the file specification for the Include field.
		* Click Save to save the details for this step.
		
* Add a third step to move the file to the target directory.
	* Use the filter again and search for "Move directory".
	* Drag and drop the "Move Directory" step and drop on the line between the "Download Artifacts" step and "Finish".
	* Click on the pencil icon to edit the details of the step.
		* You may change the name if you desire.
		* Verify that there is a period (.) in the Source Directory field.
		* Enter "C:\TEMP\DEV" in the Destination Directory field.
		* Enter \*\*/\* in Include Files field.
		* Click OK to save the step.
	* Click "Save" at the top left of the canvas to save the steps of the process.

## Applications
**TODO** Define an application.

### Create an Application
* Click "Applications" in the top row of tabs.
* Click "Create Application".
* Name: Hello-World-app"
* Click "Create" button.
* Hello-World-app new appears in the table of applications.


### Add the components to the Application
* Click on "Hello-World-app" in the list of applications.
* In the second row of tabs, click on "Components"
* Click on "Add Component".
* Select "hello-world-html" from the dropdown menu.
* Click "Save".
* "hello-world-html" is now listed as a component for the application.

### Create the environments
Create an environment for deployment.

* Click on "Environments" in the second row of tabs.
* Click on "Create Environment" button.
	* Name: DEV  
	* Select a color to represent this environment.
	* Click "Save".
* Click on the name of the new environment (DEV).  This will take you to a web page where you can specify details about the environment.
	* Click on "Add Base Resources".  
	* Select "Hello-World" from the list of Top Level environments.
	* Hover your mouse on this line.  When "Actions" appears, click on this, then select "Add Agent"
	* Add your agent.  You have now mapped an agent to this environment.
	* Hover on the line with your agent.  When Actions appears, click on this dropdown and add the component "hello-world-html" to the agent.   Click "Save".  You have mapped the component to this agent.


### Create the Application Process
**TODO** Describe the differenc between component and application processes.

* Click on "Create Process" button.
* Name: Deploy Hello World
* Click "Save".
* This will present you with the drag and drop canvas for creating the Application Process.
* Select "Install Component" from the palete on the left. Drag and drop onto the canvas.
* Click on the pencil icon to edit this step.  
	Because you have only one component and one process for that component, UCD has filled in the prompts for you.  Click "OK" to save this step.
*	Click "Save" at the top left of the canvas to save the application proess.


## Deploy the Application
### Application > Environments
* Click on the play button to request a deployment.
* Select the version to deploy
* Press "**?** " to deploy.  **TODO**
* Expand the twisties to observe the progress of the deployment processes.

# Lab 2
## Modify to allow deployment to other environments
*  Create **TEST**
	* Click on "Create Environment"
		* Name: TEST  
		* Select a color to represent this environment.
		* Click "Save".
		* Click on the name of the new environment (TEST).  This will take you to a web page where you can specify details about the environment.
		* Click on "Add Base Resources".  
		* Select "Hello-World" from the list of Top Level environments.
		* Hover your mouse on this line.  When "Actions" appears, click on this, then select "Add Agent"
		* Add your agent.  You have now mapped an agent to this environment.
		* Hover on the line with your agent.  When Actions appears, click on this dropdown and add the component "hello-world-html" to the agent.   Click "Save".  You have mapped the component to this agent.


# Lab 3
## Modify to replace tokens.

# Lab 4
## Modify with additional component for images.