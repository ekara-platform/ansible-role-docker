Role Name
=========

Role to install Docker.

Requirements
------------

Pre-requisites: setup should be done to load ekara variables.

Role Variables
--------------

- **ekara_docker_proxy**: proxy information (http\_proxy, https\_proxy, no\_proxy). Example: http_proxy: http://user:password@myproxy.com:80
- **ekara_docker_params**: All docker paramaters. See: https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-configuration-file 
- **ekara_docker_ca_cn**: CN used to create a CA.
- **ekara_docker_provider**: Map which contains private\_ip and public\_ip for the dockerhost. (See *ekara_provider_map*)

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
    	tasks:
		  include_role:
		    name: ekara.docker
		  vars:
			ekara_docker_proxy: 
			ekara_docker_params: 
				log-driver: json-file
				log-opts: 
				  max-size: "20m"
				  max-file: "3"
			ekara_docker_ca_cn: "docker_host"
			ekara_docker_provider: "{{ekara_provider_map}}"

License
-------

MIT

Author Information
------------------

https://github.com/ekara-platform/ansible-role-docker
