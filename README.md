# Cloud Foundry RabbitMQ Community Plugins Install

## How to use

1. Modify [cf-rabbitmq](https://github.com/pivotal-cf/cf-rabbitmq-release) release stub:

	```yaml
	releases:
	- name: rabbitmq-community-plugins-install
	  version: latest

	meta:
	  default:
	    rabbitmq_server:
	      templates:
	      - release: rabbitmq-community-plugins-install
	        name: rabbitmq-plugins
	      - release: cf-rabbitmq
	        name: rabbitmq-server

	properties:
	  rabbitmq-plugins:
	    list:
	      rabbitmq_delayed_message_exchange: "https://www.rabbitmq.com/community-plugins/v3.6.x/rabbitmq_delayed_message_exchange-0.0.1.ez"
	```

2. Deploy!

    ```
    bosh -d rabbitmq.yml deploy
    ```
