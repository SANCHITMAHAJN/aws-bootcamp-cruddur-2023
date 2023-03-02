# Week 2 — Distributed Tracing


### Notes

Traditional method logging
New method: Get the whole story of backend where zillions of things happening and what happened through distributed tracing.

Honeycomb is used to get the data through API Keys
Export API keys in the CDE env. (reopen workspace so its properly saved)

Recommended to add the service_name in docker-compose as its specific to a service, and attaching it to the backend service makes more sense.
Whole project needs same API key but diff names for services


otel variables in backend-flask part of docker-compose

Open Telemetry is open standard and you can swap out the endpoints. AWS Xray has own standard but making it open telemetry compatible.

honeycomb python api install added to requirements.txt

Add tracer in home_activities.py


span sets
