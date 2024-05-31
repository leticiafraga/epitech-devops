# Chocolatine

Docker and Docker Compose practical activity for a simple web poll application.
- 3 Dockerfiles
- 1 Docker Compose

The application is composed of 5 given elements:
- Poll, a Flask Python web application that gathers votes and push them into a Redis queue.
- A Redis queue, which holds the votes sent by the Poll application, awaiting for them to be
consumed by the Worker.
- The Worker, a Java application which consumes the votes being in the Redis queue, and stores
them into a PostgreSQL database.
- A PostgreSQL database, which (persistently) stores the votes stored by the Worker.
- Result, a Node.js web application that fetches the votes from the database and displays the... well, result. ;)