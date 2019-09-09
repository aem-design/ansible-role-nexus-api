# Ansible Role: Nexus Api

[![Build Status](https://travis-ci.org/aem-design/ansible-role-nexus-api.svg?branch=master)](https://travis-ci.org/aem-design/ansible-role-nexus-api)

Interact with Nexus OSS api
> This role was developed as part of
> [AEM.Design](http://aem.design/)

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name                	| Required 	| Default                                                          	| Notes                               	|
|---------------------	|----------	|------------------------------------------------------------------	|-------------------------------------	|
| nexus_host          	|          	| localhost                                                        	|                                     	|
| nexus_port          	|          	| 8081                                                             	|                                     	|
| nexus_api_path      	|          	| /service/extdirect                                               	|                                     	|
| nexus_api_url       	|          	| http://{{ nexus_host }}:{{ nexus_port }}{{ nexus_api_path }}     	|                                     	|
|                     	|          	|                                                                  	|                                     	|
| nexus_api_login_url 	|          	| http://{{ nexus_host }}:{{ nexus_port }}/service/rapture/session 	|                                     	|
|                     	|          	|                                                                  	|                                     	|
| nexus_username      	|          	| admin                                                            	|                                     	|
| nexus_password      	|          	| admin123                                                         	|                                     	|
|                     	|          	|                                                                  	|                                     	|
| wait_delay          	|          	| 1                                                                	| how long to wait between retries    	|
| wait_timeout        	|          	| 300                                                              	| how long to wait before terminating 	|


## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - {
    role: nexus-api,
    api_action: "createrepo",
    repo_check_url: "http://localhost:5000/v1/_ping",
    body: {
      "action": "coreui_Repository",
      "method": "create",
      "data": [
        {
          "attributes": {
            "docker": {
              "httpPort": "5000",
              "v1Enabled": true
            },
            "storage": {
              "blobStoreName": "default",
              "strictContentTypeValidation": true,
              "writePolicy": "ALLOW"
            }
          },
          "name": "privateregistry",
          "format": "",
          "type": "",
          "url": "",
          "online": true,
          "checkbox-1361-inputEl": true,
          "checkbox-1364-inputEl": false,
          "recipe": "docker-hosted"
        }
      ],
      "type": "rpc",
      "tid": 22
    }
  }
  - {
    role: nexus-api,
    api_action: "updaterepo",
    body: {
      "action": "coreui_Repository",
      "method": "update",
      "data": [
        {
          "attributes": {
            "maven": {
              "versionPolicy":"RELEASE",
              "layoutPolicy":"PERMISSIVE"
              },
            "storage": {
              "blobStoreName":"default",
              "strictContentTypeValidation":false,
              "writePolicy":"ALLOW_ONCE"
              }
          },
          "name": "maven-releases",
          "format": "maven2",
          "type": "hosted",
          "url": "http://localhost:8081/repository/maven-releases/",
          "online": true,
        }
      ],
      "type": "rpc",
      "tid": 18
    }
  }
```

## License

Apache 2.0

## Author Information

This role was created by [Max Barrass](https://aem.design/).