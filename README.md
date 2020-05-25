# Cisco Services APIs Ansible Playbooks

## Written by John Capobianco, Francois Daigle, and Devin Sloan

Cisco has few Services APIs to get different informations

[Support API](https://developer.cisco.com/site/support-apis/)

* Bug information
* TAC case information
* End-of-X information
* Product information
* RMA information
* Software Suggestion (Gold Star)

[Services API](https://developer.cisco.com/docs/service-apis/)

* Contracts and Coverage information
* Customer information
* Inventory information
* Product Alerts (Field Notice, Security Advisory, Security Vulnerability)

[Product Security Incident Reponse Team](https://developer.cisco.com/psirt/)

* Accelerate Cisco Security Vulnerability Assessments
* Customize Cisco Vulnerability Notifications
* Use Open Security Standards

[Business Critical Insights](https://developer.cisco.com/docs/business-critical-service-apis/)

BCI portal shows various key performance indicators, trends and predictive analytic insights. The data shown on the portal is now also available through APIs.

## Onboarding Process

### SmartNet Total Care (SNTC)

Cisco account must have API Developer role

1. Log in [Cisco.com](https://cisco.com)
2. Go to Manage Profile
3. Smart Services section
4. API Developer role = Active

If not, click on Contact Company Adminstrator to know who to ask to get it.

### Cisco API console

Create an application add assign APIs

* Log in [Cisco API console](https://apiconsole.cisco.com)
* Go to My Apps & Keys
* Register a New App

  * Name of your application: <Name Your Application>
  * OAuth2.0 Credentials: Client Credentials

* Save
* Add APIs to the application

  * Hello API
  * Software Suggestion API V2

* I agree to the terms and service
* Save

Please take note of:

* KEY: OAuth2.0 {{ client_id }}
* CLIENT_SECRET: OAuth2.0 {{ client_secret }}

### Prerequisites

1) Install Ansible

$ pip install --user ansible

2) Check version of Ansible 

$ansible --version
ansible 2.9.1

3) Clone the Repository 

git clone https://github.com/automateyournetwork/CiscoAPI.git

### RecommendedRelease.yml 

![Alt text](/screenshots/RR.png?raw=true "RecommendedRelease.yml")

1) Run ansible-playbook RecommendedRelease.yml

2) Supply Client ID (obtained from Cisco.com API dashboard)

3) Supply Client Key (obtained from Cisco.com API dashboard)

4) Provide Git Commit Message when prompted

5) Provide Git repository credentials when prompted

6) Check output .CSV files

You can pass a maximum of 10 comma separated PIDs. The playbook currently has 2 groups with a variety of example PIDs. Simply replace them with your own PIDs.

The playbook is expecting to be in a Git repository and automatically performs the Git Add, Commit, and Push at the end of the playbook.

### SerialToInfo.yml

![Alt text](/screenshots/S2Info.png?raw=true "Serial2Info.yml")

1) Run ansible-playbook SerialToInfo.yml

2) Supply Client ID (obtained from Cisco.com API dashboard)

3) Supply Client Key (obtained from Cisco.com API dashboard)

4) Supply a single or up to 10 comma separated serial numbers

5) Provide Git Commit Message when prompted

6) Provide Git repository credentials when prompted

7) Check output .CSV files

The playbook is expecting to be in a Git repository and automatically performs the Git Add, Commit, and Push at the end of the playbook.
