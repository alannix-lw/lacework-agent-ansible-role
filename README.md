# lacework-agent-ansible-role

Install the Lacework agent on systems using the yum or apt package manager.

## Role Variables

**_Required_**

lacework_accessToken

**_Optional_**

lacework_autoUpgrade\
lacework_checkfreq\
lacework_cmdAllow\
lacework_cmdDisallow\
lacework_cpuLimit\
lacework_dbSize\
lacework_fimFilePath\ (List)
lacework_fimFileIgnore\ (List)
lacework_interfaceConnectionSize\
lacework_memLimit\
lacework_perfMode\
lacework_proxyUrl

lacework_tags (Dictionary)

Note: All lacework_tags values should be quoted. Booleans will not work unless they are quoted.

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    ---
    - hosts: lacework_servers
      become: yes
      roles:
        - alannix_lw.lacework_agent_ansible_role
      vars:
        - lacework_accessToken: "your token"
        - lacework_tags:
            foo: bar
            test: "true"

## License

MIT
