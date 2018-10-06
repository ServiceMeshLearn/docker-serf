docker-serf
==================

Base docker image to run a serf (http://www.serfdom.io) agent


Usage
-----

To create the image `lukelau/serf`, execute the following command on the docker-serf folder:

	sudo docker build -t lukelau/serf:0.8.1 .

Running the Serf agent
------------------------

Run the `/run.sh` script to start serf (via the Docker supervisor):

	ID=$(sudo docker run -d -p 7946 -p 7373 lukelau/serf:0.8.1 /run.sh)

It will store the new container ID (like `d35bf1374e88`) in $ID. Get the allocated external port:

	sudo docker port $ID 7946


It will print the allocated port (like 4751). Test your deployment:

	serf join 0.0.0.0:4751

Done!


