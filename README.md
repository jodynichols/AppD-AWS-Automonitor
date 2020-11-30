# AppD Automonitor for AWS RDS

Built for NTT by Jody Nichols based on our [Cloud Kickstarter](https://github.com/Appdynamics/AppD-Cloud-Kickstart) content.

## Installation


### Get Environment Ready
Set environment variables. I created a file as below and then `source` it before running the install files. 

```sh
#!/usr/bin/bash

#----- FOR MACHINE AGENT -----
#PROVIDE USERNAME AND PASSWORD AS ARGUMENT 1 AND 2, RESPECTIVELY
export appd_username="$1"
export appd_password="$2"

#SET DEFAULTS HERE
export appd_controller_host="<YOUR CONTROLLER URL HERE>"
export appd_controller_port="443" 
export appd_machine_agent_controller_ssl_enabled="true"
export appd_machine_agent_account_access_key="<YOUR KEY HERE>"
export appd_machine_agent_account_name="<YOUR CUSTOMER NAME HERE>"
export appd_machine_agent_config="true"
export appd_machine_agent_user="centos"

#----- FOR EXTENSION -----
export AWS_ACCESS_KEY_ID="<YOUR ACCESS KEY HERE>"
export AWS_SECRET_ACCESS_KEY="<YOUR SECRET KEY HERE>"
export appd_aws_rds_extension_aws_regions="ap-southeast-2"
```
### Install the Agent and Extension

Run install by executing the scripts (make sure the user has access to /opt/) in this order:

1. install_centos7_appdynamics_machine_agent.sh
2. install_appdynamics_aws_rds_monitoring_extension.sh  

### Run Machine Agent

Browse to /opt/appdynamics/machine-agent and run `java -jar machineagent.jar`