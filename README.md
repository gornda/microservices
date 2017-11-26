# microservices

Educational repository. Allows to prepare docker image for sample application with prometheus monitoring and run it on GCP.

Pre-conditions:

1. Install  Google Cloud SDK from https://cloud.google.com/sdk/
2. ```gcloud init``` (choose your google project)
3. ```gcloud auth application-default login``` (choose your google account in browser)
4. use command from this gist to create remote docker machine https://gist.github.com/gornda/54238bddbbab907e942fe1e90d0fa41a (replace infra-179031 by your google project name)


Usage:
1. Clone this repository
2. ```cd microservices```
2. ```docker-machine ls```
3. ```eval $(docker-machine env vm1)```
3. Create .env file and fill in variablies data (you can use example.env file as example)
4. ```source .env```
4. Enter to comment, ui and post-py directories and run ```bash docker_build.sh``` in each of them
4. Enter to prometheus directory and run ```docker build -t <your_dockerhub_name>/prometheus .```
4. Move to root project directory
4. Run ```docker-compose up -d```

To check: Open browser and type "your_instance_ip":9292 - sample application should appear, type in browser "your_instance_ip":9090 - prometheus web interface should appear.
