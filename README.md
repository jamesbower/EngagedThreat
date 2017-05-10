# Overview
The purpose of this is app is to provide dashboards and metrics to aid in increasing the engagement of attackers on your SSH honeypot. The goal of the metrics is to allow you to observe the behavioral changes of the attackers when configuration changes are made to the honeypot. By increasing the engagement level of your attackers you should be able to obtain higher quality threat intelligence than a default installation while still remaining low-interaction.

# Details
In order to fully utilize the visualizations in Engaged Threat you will need to install the "Sankey Diagram - Custom Visualization” App located here - 

https://splunkbase.splunk.com/app/3112

Restart Splunk after you’ve installed the above app.

# Key Notes
The Engaged Threat Splunk App is built using the JSON logging from Cowrie SSH Honeypot. Cowrie is an SSH honeypot that was forked from Kippo by Michael Oosterhof and can be found here.

https://github.com/micheloosterhof/cowrie

# Sensor Installation
These installation instructions are assuming that you have already have a working Cowrie SSH Honeypot up and running. To start analyzing Cowrie's logs in the Engaged Threat Splunk App you simply have to run the splunk_forwarder.sh script, which will install the Splunk Universal Forwarder on your honeypot sensor, along with configuring the inputs and outputs necessary to start viewing the logs in the Engaged Threat App.

To get started, follow the commands below and enter the necessary information when prompted.

<pre><code>git clone https://github.com/jamesbower/EngagedThreat.git /tmp/engagedthreat
chmod +x /tmp/engagedthreat/splunk_forwarder.sh
cd /tmp/engagedthreat/
./splunk_forwarder.sh</code></pre>

# Using the Engaged Threat Splunk App
When you open up the Engaged Threat Splunk App you’ll be taken to the “Overview” section of the app by default. You will see that the app contains three other sections. The second section is “Session Analysis” and the third is “Session Engagement”. The fourth and final section of the app is the typical Splunk “Search” section. An synopsis of each section is provided below.

# Overview
The “Overview” section provides some key analytics consisting of the following.

* Successful Sessions
* Human Attackers
* Bots
* Average Session Duration in Minutes
* Percentage of New Sessions 
* Bounce Rate
* Chart of New Attackers vs Returning Attackers
* Top Successful Commands
* Top Failed Commands

# Session Analysis
* Successful Sessions with Interaction
* Session Flow
* Cyber Kill Chain
* Commands Entered During Session
* Session Duration in Minutes
* Files Downloaded During Session

# Session Engagement
* Unique Sessions
* Commands
* Unique Session Duration
* Session Window Size
* Top Session Flow Over 24 Hours

# To-Do
* Provide A/B Split testing of multiple sensors with different configurations.
* Find a better way to calculate “Successful Sessions”.
* Speed up queries and overall speed of the app.
* Add the ability to manage remote sensors.
* Expand Cyber Kill Chain integration.

# Known Issues
* Depending on the time frame used the “Average Session Duration” query takes a long time to calculate. I’m hoping to speed this up in the future.

# Credits
* https://splunkbase.splunk.com/app/3112/#/details for the Sankey Diagram
* https://github.com/micheloosterhof/cowrie Michael Oosterhof’s Cowrie SSH Honepot
* http://virustotal.com/ for an unbelievable intelligence source
* Brian Warehime for his continual contributions to the infosec community - https://twitter.com/brian_warehime
