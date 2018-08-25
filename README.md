# Drupal 8 PatternLab Sample
--------

This project works as a sample integration between different technologies as a startpoint
to work on a Drupal 8 project.

## What it's all about

Different technologies together, including:

* Docker[]
* Drupal

# Before you begin

You might need to add the following urls pointing to your local on the hosts file:
* d8.patternlab.local
* node.d8.patternlab.local

# Steps to get it running

1. Start by cloning this project.
2. Once the project has downloaded run:
```docker-compose up``` 
This should build the containers and start them once downloaded.
3. On a separate terminal window, run:
```docker exec -ti drupal_patternlab_php bash```
This command will allow you to go into the PHP + NodeJS container.
4. You will be at the root folder, run: 
```cd drupal```
To go into the drupal folder.
5. Run composer setup:
```composer install```
This should begin setting up Drupal core plus any additional requirement.
6. As soon as it completes run:
```cd docroot/themes/custom/emulsify_sample```
To go into the Patternlab project using Emulsify as base.
7. Install Patternlab dependiencies. Run:
```yarn install```
This will take care of installing all the libraries to make Patternlab work.
8. Once completed, run:
```yarn start```
This will take care of setting up the Patternlab server.
9. Proceed to install Drupal and create a sample landing page.
The standard link to access Drupal should be http://d8.patternlab.local:8000/
To access Patternlab the url should be http://node.d8.patternlab.local:3000/pattern-lab/public