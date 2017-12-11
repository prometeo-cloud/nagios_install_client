# nagios_install_client

## Description:

This role install Nagios client and generate hosts/checks.

## Behaviour:

Deploying the Nagios Server.

**Feature:** Creates/Installs/Configures a Nagios Client  
- **Given**a Host for client
- **Given**a repository link for additional packages
- **When** deployment is executed
- **Then** Nagios NRPE and Common Plugins are installed  
- **Then** Nagios NRPE client configuration file is setup
- **Then** Nagios NRPE Services are restarted


## Configuration:

Variable required upon execution of the role (not in the vars or defauls folders).
Needs to be provided to the role before execution.

| Variable  | Description  | Example  | 
|---|---|---|
| **nrpe_tcp_port** | The nrpe port | 5666 |
| **nagios_client_hostname** | The Nagios Client Hostname |  |
| **nagios_client_hostname** | The Nagios Server Hostname |  |
| **nagios_server_hostname** | The Nagios Server Hostname |  |

## Usage:

How to invoke the role from a playbook:

```yaml
- name: Creates Nagios Client              
  include_role:
    name: nagios_install_client
  vars:
    nagios_server_hostname: '?'
   
```