# Drupal 8 PatternLab Sample
--------

This project works as a sample integration between different technologies as a startpoint
to work on a Drupal 8 project.

## What it's all about

Different technologies together, including:

* Docker
* LAMP setup
* Drupal
* NodeJS
* SASS
* PatternLab
* BrowserSync

## Prerequisites

In order for this to work your computer should be setup in a way that allows you to run
a Drupal website locally.

Additionally, you need to be able to run NodeJS (tested with 8.10).

If you don't know much about how to configure your computer to do this, then the recommended
approach is to work with Docker. Otherwise feel free to skip the Docker section.

## Docker

Docker installation is optional. If your environment is already configured to run a Drupal
website and NodeJS you can skip the docker related steps.

Otherwise, you might want to setup docker on your environment first.

* [Docker for Mac](https://docs.docker.com/docker-for-mac/install/)
* [Docker for Linux](https://docs.docker.com/install/#releases)
* [Docker for Windows](https://docs.docker.com/docker-for-windows/install/)

After setting up Docker, update your hosts (On OSX or Linux at /etc/hosts, on Windows at
 %WinDir%\System32\Drivers\Etc\hosts) file so that they point to your localhost.
 * d8.patternlab.local
 * node.d8.patternlab.local

## Getting started

### Only if docker is available

1. Start by cloning this project.
2. Once the project has downloaded run:
```docker-compose up``` 
This should build the containers and start them once downloaded.
3. Once the containers have been initialized, on a new terminal window, run:
```docker exec -ti drupal_patternlab_php bash```
This command will allow you to go into the PHP + NodeJS container. You can proceed
within the container to execute the following steps.

### Building Drupal

1. Go to the project root folder. There run: 
```cd drupal```
To go into the drupal folder.
2. Run composer setup:
```composer install```
This should begin setting up Drupal core plus any additional requirement.

### Building the Emulsify based sample theme

1. While being at the Drupal folder, run:
```cd docroot/themes/custom/emulsify_sample```
To go into the Patternlab project using Emulsify as base.
2. Proceed to install Pattern Lab dependiencies. Run:
```yarn install```
This will take care of installing all the libraries to make Patternlab work.
3. Once completed, run:
```yarn start```
This will take care of setting up the Patternlab server.

## Testing Pattern Lab
If you are running the project from Docker and after the domains have been added to your
hosts file, the following URLs are available:
 
- http://d8.patternlab.local:8000 => Drupal site
- http://node.d8.patternlab.local:8000 => Pattern Lab Styleguide 

However, if you are running this locally, it will depend on how you set it up. When starting
Pattern Lab, it should automatically open the browser on the styleguide. Most likely it should 
be something like http://127.0.0.1:3000/pattern-lab/public

## Important note

It seems that when yarn install is executed, the Pattern Lab config file resets and disables HTML output. To enable it
again reset the project (git reset --hard HEAD) or checkout the specific file. You can confirm that the file changed
by running git status.

## Questions or issues

Feel free to open an issue and I will take a look when I have time.
