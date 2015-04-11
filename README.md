# newrelic-pcf-java-agent-tile
==========================================================
- - -

This repository contains a Pivotal Cloud Foundry Tile that allows you to automatically bind New Relic java agent with your java applications in PCF on-prem environment.


##Prerequisites

*    A New Relic account
*    A New Relic valid license key. You can obtain the license key from your New Relic account under 'Account Settings'
*    An on-prem Pivotal Cloud Foundry environment with Ops Mgr privileges


##Installation

*    Download [Newrelic-Broker-alpha-x.x.x.pivotal](https://www.cubbyusercontent.com/pl/newrelic-pcf-java-agent-tile/_38e6209b721a47419318d805f7d9ec18 "PCF Tile for New Relic java agent")
*    Login to your PCF Ops Mgr 
*    On the left side of the page click on the button "Import a Product"
*    Select the download .pivotal tile file (i.e. Newrelic-Broker-alpha-x.x.x.pivotal)
*    Continue with the process to complete loading the tile

**Note:** The upload process might take long depending on your network connection speed. Please give it time to finish. It doesn't give you any indications during the upload, but if it fails or succeeds you will get a pop-up message.


Once the tile is loaded to the PCF environment:

*    Hover your mouse on "Newrelic Service Broker Alpha v-x.x.x, and select the "Add" b utton to add the tile
*    Click on New Relic Tile that was added to the page
*    Under "Settings" tab select "Service Broker Application"
*    Enter your New Relic license key and click the "Save" button
*    Go back to "Installation Dashboard" (link on top left of the page)
*    Click the big blue "Apply Changes" button on top right of the page. This will take about 30 minutes to finish.
*    Once changes are applied, the tile will be available in the 'Marketplace'


## Use New Relic java agent Tile in PCF

*    Login to your PCF console
*    Select your "Org" (and "Space")
*    Go to Marketplace
*    Select "New Relic" Tile and click on "Select this plan" button
*    Fill in the "Instance Name"
*    Select the space you'd like to use
*    Select the application to which to bind the service
*    Click the "Add" button
*    From your system connect to CF
**    cf api <CF_API_ENDPOINT> [--skip-ssl-validation]
**    cf login -u <USER> -p <PASSWORD>
*    restage the application you just bound to the service
**    cf restage <APPNAME>


**Note:** After the initial time that the service is added to the space, you can just go to the intended space, scroll down to the bottom of the page, select "Services" tab, and click on "+Bind a Service" button.


