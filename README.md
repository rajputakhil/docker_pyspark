# docker_spark

# Software Installation Directions #

## Setup Using Docker ##

1. Install docker using the following URL

https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce-1

2. Pull the Docker image

    $ docker pull jupyter/pyspark-notebook

Verify

    $ sudo docker images

## Running Docker Images ##

    $ sudo docker run -it -p 8889:8888 -v /media/akhil/750GB/Courses/Coursera/dlaicourse:/home/ucsddse230/work ucsddse230/cse255-dse230 /bin/bash
    
    $ sudo docker run --rm -it -p 8889:8888 -v "$PWD":/home/ucsddse230/work ucsddse230/cse255-dse230 /bin/bash
    
    $ sudo docker run --rm -p 10000:8888 -e JUPYTER_ENABLE_LAB=yes -v "$PWD":/home/jovyan/work jupyter/datascience-notebook:9b06df75e445

This command will:

1. Start the docker container

2. mount the local directory ""$PWD" inside the container at the location "/home/ucsddse230/work"

3. Forward requests to port 8889 on the local system from port 8888 inside the docker container.

Run the following commands to start jupyter at http://localhost:8889 by issuing the command

    $ jupyter notebook

This will start jupyter at port 8888 inside the docker container, which will be accessible outside the docker at port 8889.

Go ahead open your web browser and put "localhost:8889" in the address bar. You should now be able to see the Jupyter Notebook webpage.
