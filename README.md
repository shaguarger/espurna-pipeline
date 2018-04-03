# ESPurna Firmware - concourse build and deploment pipeline

This concourse pipeline is used for building and deploying nine H801 controllers with the current ESPurna version. Build and nine deployments take about 4 minutes in total depending on your hardware.

## Setup concourse docker 
- git clone https://github.com/concourse/concourse-docker.git
- docker-compose up -e CONCOURSE_BASIC_AUTH_USERNAME=[username] -e CONCOURSE_BASIC_AUTH_PASSWORD=[password]

## Setup pipeline
Clone this pipeline and configure vars.yaml (see template)

## Deploy pipeline
Download fly for concourse and login with credentials
- fly -t [concourse-server] login
- fly -t [concourse-server] set-pipeline -c pipeline.yaml -p espurna

## Start deployment
Go to your concourse and start the first deployment with (+).