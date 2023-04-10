# Kafka for Beginners


Installing Docker with IntelliJe

https://www.jetbrains.com/help/idea/docker.html#connect_to_docker

Problem1 : Change ownership of docker to current user

Description 
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running? (Details: [13] Permission denied)

Solution 
sudo chown yogesh:docker /var/run/docker.sock

https://phoenixnap.com/kb/cannot-connect-to-the-docker-daemon-error


Problem 2 : change config.json file to run the compose file

Description 
error getting credentials - err: exec: "docker-credential-desktop": executable file not found in $PATH, out: ``

Solution 
sudo nano ~/.docker/config.json
change credsStore -> credStore 
Save and exit 


Run from IntelliJe 
In docker-compose.yml -- check services command run it 
It will run all the containers and download its images as mentioned in docker-compose.

Wikimedia stream UI page that will be used to check info for stream data stats, 
https://codepen.io/Krinkle/pen/BwEKgW?editors=1010


Event source for wikimedia 
https://esjewett.github.io/wm-eventsource-demo/

https://wikitech.wikimedia.org/wiki/Event_Platform/EventStreams


Wikimedia Producer Implementation 

Import OkHttp event source library 

OkHttp EventSource is a Java library that provides an implementation of the Server-Sent Events (SSE) protocol, which is a unidirectional communication protocol for real-time updates over HTTP. It allows clients to subscribe to a stream of events sent from a server and receive real-time updates without needing to repeatedly poll the server for new data.
The OkHttp EventSource library provides a simple API for creating and managing SSE connections. The library handles the low-level details of establishing and maintaining a connection to an SSE server, parsing incoming events, and dispatching them to registered listeners.
To run producer wikimedia 
Run local conductor with Intellije ( docker-compose )
Then access localhost:8080 ( create new topic wikimedia.recentchange )
Run application WikimediaChangesProducer
Refresh the new topic created, we will have lots of event msg from wikimedia stream which was listened and produced through this code.
