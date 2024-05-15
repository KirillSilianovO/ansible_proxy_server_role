Ansible Role for proxy server
=========

Ansible role for installing and configuring a proxy server, based on Squid.

Requirements
------------
- Docker installed and configured

Role Variables
--------------
- `apps_root_dir` - Root directory for the applications. Default is `/opt/apps`
- `proxy_server_version` - Version of the proxy server image to install. Default is `latest`
- `proxy_server_port` - Port for the proxy server to listen on. Default is `8080`
- `proxy_server_credentials` - List of credentials for the proxy server. Default is `user:changeme`. Example:
```yaml
proxy_server_credentials:
    username: user
    password: changeme
```

Dependencies
------------

- community.docker

Example Playbook
----------------
```yaml
- hosts: servers
  roles:
     - role: proxy-server
       vars:
         proxy_server_port: 8080
         proxy_server_credentials:
           - username: user
             password: changeme
```
License
-------

Apache
