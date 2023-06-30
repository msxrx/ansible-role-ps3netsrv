# ansible-role-ps3netsrv

Ansible Role - ps3netsrv

This role automates provisioning of the [PS3 NET server](https://github.com/aldostools/webMAN-MOD/wiki/~-PS3-NET-Server). It is based on the [ps3netsrv docker container](shawly/docker-ps3netsrv), refer to its README for most issues. It creates required directories, sets up the container and starts it.

## What's this? I'm confused

- ps3netsrv is an application that lets you stream content to your PS3
- Ansible is a project that lets you write automate various tasks like installing software, configuring it, etc.
- If you simply want to run the server without ansible, you can do so by downloading a ps3netsrv executable and running it yourself. The guide is [here](https://github.com/aldostools/webMAN-MOD/wiki/~-PS3-NET-Server)

## Requirements

You'll need docker installed. Using [geerlingguy/ansible-role-docker](geerlingguy/ansible-role-docker) might be a good idea.

## Role variables

```yaml
# Directory that contains individual folders for each file type
ps3netsrv_data_directory: "{{ docker_home }}/ps3netsrv"

# port that ps3netsrv will be available on
ps3netsrv_port: "38008"

# ID of the user the application runs as
USER_ID: 1000

# Group ID of the user the application runs as
GROUP_ID: 1000

# Timezone of the container
TZ: "Etc/UTC"
```

## Example Playbook

```yaml
- hosts: all

  roles:
    - msxrx.ps3netsrv
```

## License

GPLv3

## Sound cool! Where do I learn more about Ansible?

- [Wolfgang's Channel's Ansible Playlist](https://www.youtube.com/watch?v=Z7p9-m4cimg&list=PLkxWXio1KmRoZd88WbrnSnQM5MJY5PjH2)
- [Jeff Geerling's Ansible 101](https://www.youtube.com/watch?v=goclfp6a2IQ&list=PL2_OBreMn7FqZkvMYt6ATmgC0KAGGJNAN)
- [Jeff Geerling's Book - Ansible for DevOps](https://github.com/geerlingguy/ansible-for-devops-manuscript)
