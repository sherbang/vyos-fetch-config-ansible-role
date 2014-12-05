## Ansible role for VyOS fetch config.

This is an ansible role to collect configuration from VyOSs.

## Installation step

Clone this repo to your Ansible roles directory

    mkdir roles
    cd roles
    git clone https://github.com/hiroyuki-sato/vyos-fetch-config-ansible-role.git vyos


Here's an example how to use this role. create vyos_config.yml

    - hosts: all
      user: vyos
      roles: 
        - vyos

Create inventory file. ex. inventory.ini

     # VyOS IP or FQDN
    10.10.10.10


    ansible-playbook -i inventory.ini config.yml --ask-pass

## Execution example


    % ansible-playbook -i inventory.ini vyos_config.yml --ask-pass
    SSH password: 
    
    PLAY [all] ******************************************************************** 
    
    GATHERING FACTS *************************************************************** 
    ok: [10.10.10.10]
    
    TASK: [vyos | generate current config] **************************************** 
    changed: [10.10.10.10]
    
    TASK: [vyos | copy file] ****************************************************** 
    changed: [10.10.10.10]
    
    TASK: [vyos | delete conf file] *********************************************** 
    changed: [10.10.10.10]
    
    PLAY RECAP ******************************************************************** 
    10.10.10.10             : ok=4    changed=3    unreachable=0    failed=0   


You will find configuraiton file in configs directory. 

