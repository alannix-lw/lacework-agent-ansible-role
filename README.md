# lacework-agent-ansible-role

Install the Lacework agent on systems using the yum or apt package manager.

![Molecule Tests](https://github.com/alannix-lw/lacework-agent-ansible-role/actions/workflows/molecule-tests.yml/badge.svg)

## Role Variables

| Variable                         | Required | Description                                                                                                                              |
| -------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| lacework_accessToken             | Yes      | The access token to be used by the Lacework agent                                                                                        |
| lacework_autoUpgrade             | No       | A boolean representing whether the agent should automatically upgrade                                                                    |
| lacework_checkfreq               | No       | The frequency at which the agent should check for updates (in minutes)                                                                   |
| lacework_cmdAllow                | No       | A comma-separated string, with `*` wildcards, of executable paths to include from command line argument collection                       |
| lacework_cmdDisallow             | No       | A comma-separated string, with `*` wildcards, of executable paths to exclude from command line argument collection                       |
| lacework_cpuLimit                | No       | The maximum number of CPU units that the Lacework agent should use                                                                       |
| lacework_dbSize                  | No       | The size of the local Lacework agent cache database                                                                                      |
| lacework_fimFilePath             | No       | Lacework includes monitoring a set of default paths. To override the default, supply a comma-separated string of paths                   |
| lacework_fimFileIgnore           | No       | Lacework excludes monitoring a set of default paths. To override the default, supply a comma-separated string of paths                   |
| lacework_interfaceConnectionSize | No       | The size of the network connection buffer, per interface, to create. **Only modify this parameter at the direction of Lacework Support** |
| lacework_memLimit                | No       | The maximum amount of memory that the Lacework agent should use.                                                                         |
| lacework_perfMode                | No       | The Lacework agent supports a "lite" mode, which reduces CPU consumption. To enable, set this value to `lite`                            |
| lacework_proxyUrl                | No       | The Lacework agent can use a network proxy by adding proxy information in the following format: `http(s)://[proxy_server]:[proxy_port]`  |
| lacework_release                 | No       | The release branch to install. Default is `latest` but options are as follows: `latest`, `established`, or `archived`                    |
| lacework_serverUrl               | No       | The serverurl property specifies the endpoint to which the LAcework agent should communicate. ex: `https://api.fra.lacework.net`         |
| lacework_tags                    | No       | A set of key/value pairs to use as tag data for the Lacework agent. **Note: All boolean tag values should be quoted.**                   |

## Example Playbook

This role is also hosted on [Ansible Galaxy](https://galaxy.ansible.com/alannix_lw/lacework_agent_ansible_role) and can be installed using the following command:

> `ansible-galaxy install alannix_lw.lacework_agent_ansible_role`

Once the role is installed, it can be used with a simple playbook like the following:

```
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
```

## License

MIT
