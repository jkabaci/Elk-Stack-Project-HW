# Elk-Stack-Project-HW
This is a submission file for Project 1 of the UCSD Cyber Security Bootcamp
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting inbound access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the file systems of the Vms on the network and system metrics.
- _TODO: What does Filebeat watch for?_Filebeat detecs changes to the filesystem, specifically used to collect Apache logs.
- _TODO: What does Metricbeat record?_Metricbeat detects changes in the system metrics, such as CPU usage and is used to detect SSH login attempts, failed sudo escalations, and CPU/RAM statistics.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| TODO     |Web Server| 10.0.0.5   | Linux            | 
| TODO     |Web Server| 10.0.0.6   | Linux            |
| TODO     |Monitoring| 10.0.0.8   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by each other.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_I allowed the DVWA 1 machine access to the Elk VM with an IP address of 10.0.0.9

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 52.175.238.213       |
| Elk      | No                  | 10.1.0.4             |
| DVWA 1   | No                  | 10.0.0.9             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_Automating configuration with Ansible allows for easier application of the playbook throughout multiple machines. 

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Docker
- Install pip3
- Install Docker python module
- Increase Virtual Memory
- Download and Launch Docker Elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
10.0.08

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
We have installed Metricbeat and Filebeat.

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

Filebeat detects changes to the filesystem, concerning the Apache logs. Metricbeat detects changes in the system metricts, concerning CPU usage. Packetbeat collects packets that pass through the NIC, similar to Wireshak.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_It is a yml file that can be copied from git.
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running? 10.0.0.8:5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
