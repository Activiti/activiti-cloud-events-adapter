# Activiti Cloud Events Adapter

[![Join Us in Gitter](https://badges.gitter.im/Activiti/Activiti7.svg)](https://gitter.im/Activiti/Activiti7?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status Travis](https://travis-ci.org/Activiti/activiti-cloud-events-adapter.svg?branch=master)](https://travis-ci.org/Activiti/activiti-cloud-events-adapter)
[![Coverage Status](http://img.shields.io/codecov/c/github/Activiti/activiti-cloud-events-adapter/master.svg?maxAge=86400)](https://codecov.io/gh/Activiti/activiti-cloud-events-adapter)
[![ASL 2.0](https://img.shields.io/hexpm/l/plug.svg)](https://github.com/Activiti/activiti-cloud-events-adapter/blob/master/LICENSE.txt)
[![CLA](https://cla-assistant.io/readme/badge/Activiti/activiti-cloud-events-adapter)](https://cla-assistant.io/Activiti/activiti-cloud-events-adapter)
[![Docker Build Status](https://img.shields.io/docker/build/activiti/activiti-cloud-events-adapter.svg)](https://hub.docker.com/r/activiti/activiti-cloud-events-adapter/)
[![Known Vulnerabilities](https://snyk.io/test/github/Activiti/activiti-cloud-events-adapter/badge.svg)](https://snyk.io/test/github/Activiti/activiti-cloud-events-adapter)
[![security status](https://www.meterian.com/badge/gh/Activiti/activiti-cloud-events-adapter/security)](https://www.meterian.com/report/gh/Activiti/activiti-cloud-events-adapter)
[![stability status](https://www.meterian.com/badge/gh/Activiti/activiti-cloud-events-adapter/stability)](https://www.meterian.com/report/gh/Activiti/activiti-cloud-events-adapter)

Activiti Cloud Events Adapter Implementation.  This service converts events emitted by Runtime Bundles to an Alfresco event format and routes them to the Alfresco internal Message Broker (ActiveMQ).

As all our services, this module was build using the [activiti-cloud-starter-events-adapter](https://github.com/activiti/activiti-cloud-events-adapter-service) module, that you can use to create your own version of this service as with any other Spring Boot Starter.

TODO - link to Activiti & Activiti Cloud GitBook

[Docker Image](https://hub.docker.com/r/activiti/activiti-cloud-events-adapter/)

## Building & Running this Service
You can build this service from source using Git & Maven or you can just run our Docker Image. 

### Spring Boot: 
> git clone https://github.com/Activiti/activiti-cloud-events-adapter.git
> cd activiti-cloud-events-adapter/
> mvn clean install spring-boot:run

### Docker: 
> docker run -p 8181:8181 -d --name activiti-cloud-events-adapter activiti/activiti-cloud-events-adapter:latest

## Environemnt Variables
```
spring.application.name=${ACT_EVENTSADAPTER_APP_NAME:audit}
spring.cloud.stream.bindings.eventsAdapterConsumer.destination=${ACT_EVENTSADAPTER_CONSUMER_DEST:engineEvents}
spring.cloud.stream.bindings.eventsAdapterConsumer.group=${ACT_EVENTSADAPTER_CONSUMER_GROUP:eventsAdapter}
spring.cloud.stream.bindings.eventsAdapterConsumer.contentType=${ACT_EVENTSADAPTER_CONTENT_TYPE:application/json}
activiti.cloud.events.adapter.topic.host=${ACT_ACTIVEMQ_HOST:activemq}
activiti.cloud.events.adapter.topic.port=${ACT_ACTIVEMQ_PORT:61616}
activiti.cloud.events.adapter.topic.topicName={ACT_ACTIVEMQ_TOPIC:alfresco.events.source}
activiti.cloud.events.adapter.topic.username={ACT_ACTIVEMQ_USERNAME:}
activiti.cloud.events.adapter.topic.password={ACT_ACTIVEMQ_PASSWORD:}
spring.rabbitmq.host=${ACT_RABBITMQ_HOST:rabbitmq}
spring.rabbitmq.port=${ACT_RABBITMQ_PORT:5672}
spring.rabbitmq.username=${ACT_RABBITMQ_USERNAME:guest}
spring.rabbitmq.password=${ACT_RABBITMQ_PASSWORD:guest}
spring.rabbitmq.virtual-host=${ACT_RABBITMQ_VIRTUAL_HOST:/}

```