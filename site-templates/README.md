# Bluescape Ambassador v3 devportal-content

User content for Ambassador Edge Stack Dev Portal

Site for the Bluescape Developer Portal.
Current site URL: https://developer.bluescape.com/

## How to customize

- Fork this repository.

- Update the `DEVPORTAL_CONTENT_URL` environment variable in your Ambassador Edge Stack deployment.

## Kinds of content

Kinds of information you can put on dev portal:

| Kind               | Location                     | Preprocessing | Go templates |
| ------------------ | ---------------------------- | ------------- | ------------ |
| landing page       | `/landing.gomd`              | Markdown      | Yes          |
| page               | `/pages/`_name_`.gomd`       | Markdown      | Yes          |
| site layout        | `/layout.gohtml`             |               | Yes          |
| template fragments | `/fragments/`_name_`.gohtml` |               | Yes          |
| CSS stylesheets    | `/styles/`                   |               | No           |
| Assets             | `/assets/`                   |               | No           |

## NOTE:

If you notice the devportal service not starting when you are running docker-compose up, you can ignore that unless you have some dependency on devportal. As of 04/08/2021, no other services have a dependency on the developer portal for local development.
If you do need to run the developer portal, see the sections below.

## Running locally with docker-compose

This section assumes you have already set up your docker-compose correctly, locally. If not, first follow the instructions here: https://confluence.common.bluescape.com/confluence/display/cip/Docker+Compose+Quick+Start

First, clone the repo locally (at the same level as your infrastructure repo was cloned):

> git clone git@github.com:Bluescape/developer-portal.git

There is no need to build the devportal service locally - it comes up automatically if you bring up docker-compose:

> docker-compose up

## Running locally WITHOUT docker-compose

You can also work locally with the devportal without using docker. To do so, first clone the repo locally:

> git clone git@github.com:Bluescape/developer-portal.git

Next, cd into site-templates:

> cd developer-portal/site-templates

Then, run the following:

> docker run -it --rm --volume $PWD:/content --publish 8877:8877 docker.io/datawire/ambassador_pro:local-devportal-0.11.0

Access the service in your browser at:

> localhost:8877
