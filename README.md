# newrelic-pcf-java-agent-tile
==========================================================
- - -

This repository contains a Pivotal Cloud Foundry Tile that allows you to automatically bind New Relic java agent with your java applications in PCF on-prem environment.


##Prerequisites

*    One or more New Relic accounts/sub-accounts
*    A New Relic valid license key for each account/sub-account. You can obtain the license key for each accountfrom your New Relic account under 'Account Settings'
*    An on-prem Pivotal Cloud Foundry environment with Ops Mgr privileges


##Installation

*    Download [Newrelic Service Broker Tile for java agent](http://bit.ly/1cASzcN "PCF Tile for New Relic java agent")
*    Login to your PCF Ops Mgr 
*    On the left side of the page click on the button **"Import a Product"**
*    Select the downloaded **.pivotal** tile file (i.e. Newrelic-Broker-Beta-x.x.x.pivotal)
*    Continue with the process to complete uploading of the tile

**Note:** The upload process might take long depending on your network connection speed. Please give it time to finish. It doesn't give you any indications during the upload, but if it fails or succeeds you will get a pop-up message.


Once the tile is uploaded to PCF environment:

*    Hover your mouse on **"Newrelic Service Broker Beta v-x.x.x"** on the left side, and select the **"Add"** button to add the tile
*    Click on New Relic Tile that was just added to the page
*    Under **"Settings"** tab select **"Service Broker Application"**
*    For every account or sub-account you want to add click the **"Add"**
*    Enter **"Plan Name"**, **"Plan Description"**, and your **"New Relic license key"** for each account/sub-account
*    Once you have entered plans for all desired accounts, click the **"Save"** button
*    Go back to **"Installation Dashboard"** (link on top left of the page)
*    Click the big blue **"Apply Changes"** button on top right of the page. This will take about 30 minutes to finish.
*    Once changes are applied, the tile will appear in the **"Marketplace"**


## Use New Relic java agent Tile in PCF

*    Login to your PCF console
*    Select your **"Org"** (or create new **"Org"** and **"Space"** as you wish)
*    Go to **"Marketplace"**
*    Select **"New Relic"** Tile and click on **"View Plan Options"**
*    Select the plan from the left that is associated with your desired New Relic account and click on **"Select this plan"** button
*    Fill in the **"Instance Name"**, 
*    Select the **"space"** you'd like to use
*    Select the **"application"** to which to bind the service
*    Click the **"Add"** button

## Restaging the Application
In rare cases you might need to restage the application.
*    From your system connect to CF
    *    cf api **\<CF_API_ENDPOINT\>** [--skip-ssl-validation]
    *    cf login -u **\<USER\>** -p **\<PASSWORD\>**
*    Restage the application you just bound to the service
    *    cf restage **\<APPNAME\>**
*    Login to your New Relic account to check the health of the application


**Note:** After the initial time that the service is added to the space, you can just go to the intended space, scroll down to the bottom of the page, select **"Services"** tab, and click on **"+Bind a Service"** button to use the service.


