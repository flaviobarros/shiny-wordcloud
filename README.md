Dockerized Shiny App
=======================

This is the Dockerized Shiny App Worcloud [Wordcloud](http://shiny.rstudio.com/gallery/word-cloud.html)

This Dockerfile is based on Debian "testing" and r-base image.

The image is available from [Docker Hub](https://registry.hub.docker.com/u/flaviobarros/shiny-wordcloud/).

## Usage:

To run this Shiny App on your computer:

```sh
docker run --rm -p 80:80 flaviobarros/shiny-worcloud
```

and it will avaliable at http://127.0.0.1/ ou http://localhost

You can run the container at other ports. Sometimes there is already some services running at PORT 80, as Apache ou Nginx.
To run the app at PORT 3838 for example, you can use:

```sh
docker run --rm -p 3838:80 flaviobarros/shiny-worcloud
```

## Intented usage:

This project can used as a start point to build any dockerized shiny app, the could be distributed at any server running docker.
Possible use cases are:

* Deploy a single Shiny App at AWS, Googlge Compute Engine, Azure or a private server with docker.
* Deploy Shiny Apps as any dokku-alt app. 

## Building your own Shiny App:

After developing your Shiny App, you will have two files needed to deployment: ui.R and server.R, then:

* Remove all files from the folder mypp (these files are from Wordcloud example) and put your files there, ui.R and server.R
* Build a docker image with:

```sh
docker build -t yourname/yourappname .
```

At this poit i will be able to run your app, just like Wordcloud

## Deploy with a docker based PaaS

If you have a PaaS with Dockerfiles support you can git push this image. Soon i will provide instructios to deploy with dokku-alt

## IMPORTANT

This project is not an alternative Shiny Server. It exposes PORT 80 (not 3838) and is intented to serve only single apps to easy deployment.


