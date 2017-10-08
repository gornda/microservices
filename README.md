# microservices

Educational repository. Allows to prepare docker image for sample application and run it on GCP.

Pre-conditions:

1. Install  Google Cloud SDK from https://cloud.google.com/sdk/
2. ```gcloud init``` (choose your google project)
3. ```gcloud auth application-default login``` (choose your google account in browser)
4. Create docker-host on GCP
5. Create firewall rule in your project to allow port:9292 with network tag "docker-machine" from any IP.

Usage:

1. Clone repository
2. ```cd microsevices```
3. ```docker build -t reddit:latest .```
4. ```docker run --name reddit -d --network=host reddit:latest```

Checking: Open browser and type "your_instance_ip":9292
