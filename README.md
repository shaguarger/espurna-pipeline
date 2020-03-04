# ESPurna Firmware - concourse build and deploment pipeline

This concourse pipeline is used for building and deploying H801 and SONOFF controllers with the current ESPurna version.

## Setup concourse docker 
- git clone https://github.com/concourse/concourse-docker.git
- docker-compose up -e CONCOURSE_BASIC_AUTH_USERNAME=[username] -e CONCOURSE_BASIC_AUTH_PASSWORD=[password]

## Setup pipeline
Clone this pipeline and configure vars.yml (see template)

## Deploy pipeline
Download fly for concourse and login with credentials (where target is your more convenient target name and concourse-url the url of your concourse instance, see [the docs](https://concourse-ci.org/fly.html) for more information)
- fly -t [target] login -c [concourse-url]
- fly -t [target] set-pipeline -c pipeline.yml -p espurna -l vars.yml

## Start deployment
Go to your concourse and start the first deployment with (+).
