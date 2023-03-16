# Week 2 — Distributed Tracing

This week focused on enabling logging, tracing and monitoring for our Cruddur app. Using the following tools and technologies will really help us identify errors and their root cause, assisting in faster resolution.


## Setting up Honeycomb

* Created an account on honeycomb.io and created a new environment 'bootcamp'.
* Generated API Key for the environment and set it as a variable in my Gitpod environment.
 ![honeycomb](assets/honeycomb_api.jpg)
 
 * We are using Open Source Telemetry (OTEL), and installed the dependencies required by adding the following packages to our requirements.txt file
 ![otel](assets/otel.jpg)
 
 * Added the environment keys in the docker-compose file, and restarted the workspace.
 ![envkeys](assets/env_dc.jpg)
 
 * Added the following code to app.py to fully start honeycomb tracing
![hc_app](assets/hc_app.jpg)

* Composed up our docker containers to test working and getting our first trace in the Honeycomb dashboard.
![hc_logs](assets/honeycomb_log.jpg)



## AWS Xray

* Add the required dependencies to requirements.txt

![xray_req](assets/xray_req.jpg)

* Add environment variables to the docker-compose file

![xray_dc](assets/xray_dc.jpg)

![xray_daemon](assets/xray_daemon.jpg)

* Create an xray trace group
![xray_create_group](assets/xray_create_group.jpg)

* Create a file aws/json/xray.json with the following sampling rule
![xray_json](assets/xray_json.jpg)

* Add the following command 
![](assets/xray_command.jpg)

* Add the following to app.py
![xray_app](assets/xray_app.jpg)


## AWS CloudWatch

* Add the dependencies in the requirements.txt file
![cw_req](assets/cw_req.jpg)

* Add the following to docker-compose file
![cw_dc](assets/cw_dc.jpg)

* Add the following logger command to the app.py file
![cw_app](assets/cw_app.jpg)
![cw_appp](assets/cw_app1.jpg)

* You should see the following logs:
![cw_logs](assets/cw_logs.jpg)


## Rollbar

* Create an account on Rollbar.

* Add the following dependencies to requirements.txt file:
![rollbar_req](assets/rollbar_req.jpg)

* Add the following to docker-compose file:
![rollbar_dc](assets/rollbar_dc.jpg)

* Add the following to app.py file
![rollbar_app](assets/rollbar_app.jpg)

* Compose-up the containers to check error on Rollbar:
![rollbar_log](assets/rollbar_log.jpg)


### Notes
Traditional method logging
New method: Get the whole story of backend where zillions of things happening and what happened through distributed tracing.

Honeycomb is used to get the data through API Keys
Export API keys in the CDE env. (reopen workspace so its properly saved)

Recommended to add the service_name in docker-compose as its specific to a service, and attaching it to the backend service makes more sense.
Whole project needs same API key but diff names for services

span sets
