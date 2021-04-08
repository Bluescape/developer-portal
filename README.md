# Bluescape Developer Portal

Site for the Bluescape Developer Portal.
Current site URL: https://developer.bluescape.com/

## Running locally with docker-compose
This section assumes you have already set up your docker-compose correctly, locally. If not, first follow the instructions here: https://confluence.common.bluescape.com/confluence/display/cip/Docker+Compose+Quick+Start

First, clone the repo locally (at the same level as your infrastructure repo was cloned):
    git clone git@github.com:Bluescape/developer-portal.git

There is no need to build the devportal service locally - it comes up automatically if you run this:
    docker-compose up


## Running locally WITHOUT docker-compose
You can also work locally with the devportal without using docker. To do so, first clone the repo locally:
    git clone git@github.com:Bluescape/developer-portal.git

Then, run the following:
    docker run -it --rm --volume $PWD:/content --publish 8877:8877 docker.io/datawire/ambassador_pro:local-devportal-0.11.0

Access the service in your browser at:
    localhost:8877
