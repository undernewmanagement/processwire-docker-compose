## Why use docker for LAMP apps?

I use Docker so that my dev and production envrionments are identical, as well as
making sure that any other developers will have the same environment as well.

This mgiht not be for you if you have a working MAMP, Vagrant, or Homebrew setup.

## Getting started

Note: this version is only tested on a Macbook Pro running El Capitan.

You will want to have a recent version of docker and docker-compose (April 2016).
The docker-compose.yml file uses version '2'

  1. download a version of Process wire from here: https://processwire.com/download/ (my version is 2.7.2)
  2. unzip the file into the `src/` folder
  3. rename htaccess.txt to .htaccess `mv htaccess.txt .htaccess`
  4. make sure your ./db foler is clean

The Dockerfiles in the `lamp/` and `mysql/` folders contain a customization which solves some permission issues
regarding OSX and shared volumes.

Basically, they make sure that the UID and GID for the apache and mysql user in the containers matches the UID/GID
for the user in OSX (typically 1000)

That said, if your UID is different, then you will want to cahnge the Dockerfile in both the `db/` and `mysql/` folders.




## License

See LICENSE.txt

