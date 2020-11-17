# David-Boal
Project 1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

/Users/HaydenBoal/Documents/David-Boal/Diagrams/Project 1 Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - https://bit.ly/ansible-david

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly __availablilty__, in addition to restricting __traffic__ to the network.

- _What aspect of security do load balancers protect? __DoS attacks__. What is the advantage of a jump box?_ __Creates a central access point that all administrators can connect to.__

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __logs__ and system __traffic__.

- _What does File-beat watch for?_ __log data__ (More Detail)
- _What does Metricbeat record?_ __metric data__ (More Detail)

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name         | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1      | Linux |
| Web-1      | Web Server | 10.0.0.5      | Linux |
| Web-2      | Web Server | 10.0.0.7      | Linux |
| Bigredelk  | Monitoring | 10.1.0.4     | Linux |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __Jump Box__ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
__52.118.153.253__

Machines within the network can only be accessed by __other machines in the network__

- _Which machine did you allow to access your ELK VM? __Jump Box__ What was its IP address?_ __52.118.153.253__

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | port 22        | 24.125.199.27  |
| Web-1      | port 22          | 52.118.153.253             |
| Web-2       | port 22            | 52.118.153.253              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

- _What is the main advantage of automating configuration with Ansible?_ __Automatic logins at a certain time and date__

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._

- __Create ansible playbook that installs Docker and configures an ELK container__
- __Create playbook__
- __Add Elk Vm to hosts file__
- __run playbook__

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

/Users/HaydenBoal/Documents/David-Boal/Screenshots/Docker PS.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- __10.0.0.5 10.0.0.7__

We have installed the following Beats on these machines:
- __filebeat and metricbeat__

These Beats allow us to collect the following information from each machine:

- __Filebeat - Collects data of protected files and gives an alert what there are modifications__ 
- __Metricbeat - Collects data of CPU and sends alerts of unauthorized CPU usage__

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the __yml file__ file to __playbooks__.
- Update the __host__ file to include...
- Run the playbook, and navigate to __VM__ to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_

- _Which file is the playbook? Where do you copy it?_ __yml file__ __playbook directory__

- _Which file do you update to make Ansible run the playbook on a specific machine?_ __host file__ 
- _How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ __creating a group and adding an ip tot he groups__

- _Which URL do you navigate to in order to check that the ELK server is running? __http://104.210.12.6:5601/app/kibana__

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.:_ __ansible-playbook {name of playbook}.yml__
