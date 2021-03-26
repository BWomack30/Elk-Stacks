# Elk-Stacks
This is my Elk-Stack server I created for class







Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible-playbook file may be used to install only certain pieces of it, such as Filebeat.
TODO: filebeat-playbook.yml metricbeat-playbook.yml
This document contains the following details:
Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
TODO: What aspect of security do load balancers protect? Availability 
What is the advantage of a jump box? Connect securely to web servers
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
TODO: What does Filebeat watch for? System logs
TODO: What does Metricbeat record? system and application metrics
The configuration details of each machine may be found below. Note: Use the Markdown Table Generator to add/remove values from the table.
Name
Function
IP Address
Operating System
Jump Box
Gateway
10.1.0.4
Linux
Web 1
Web server
10.1.0.5


Web 2
Web server
10.1.0.7


Elk Server
Elastic-search log-stash kibana(ELK)
10.2.0.4



Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump Box  machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Add 136.34.209.76

Machines within the network can only be accessed by Jump Box.
Which machine did you allow to access your ELK VM? What was its IP address?Jump Box, 10.1.0.4 
A summary of the access policies in place can be found in the table below.


Name
Publicly Accessible
Allowed IP Addresses
Jump Box
No
10.0.0.1 10.0.0.2
Web 1
No
10.1.0.5 on SSH
Web 2
No
10.1.0.7 on SSH
Elk Server
No
Public IP TCP 5601
Load Balancer
No
Public IP HTTP 80

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
TODO: What is the main advantage of automating configuration with Ansible? Save time
The playbook implements the following tasks:
TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc


Install Docker
Create ansible container
Install necessary programs through ansible playbook
Install filebeat and metricbeat
Open kibana container
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Target Machines & Beats
This ELK server is configured to monitor the following machines:
TODO: Web  Public 23.101.141.81 Private  10.1.0.5
	 Web 2 Public 23.101.141.81 Private 10.1.0.7

We have installed the following Beats on these machines:
TODO: filebeat and metricbeat
These Beats allow us to collect the following information from each machine:
TODO: Filebeat collects and monitors log files from different locations and IP addresses. Metricbeat takes metrics and stats and sends information to specified location. Filebeat: Error Codes Metricbeat: Network traffic
Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:
Copy the public key file to VM Password.
Update the hosts file to include...
Run the playbook, and navigate to Kibana to check that the installation worked as expected.
TODO: Answer the following questions to fill in the blanks:
Which file is the playbook? docker .yml elk.yml filebeat-playbook.yml metricbeat-playbook.yml Where do you copy it? /etc/
Which file do you update to make Ansible run the playbook on a specific machine? Config files 
How do I specify which machine to install the ELK server on versus which to install Filebeat on? Config Files
_Which URL do you navigate to in order to check that the ELK server is running? http://104.43.199.70:5601/app/kibana
As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.
