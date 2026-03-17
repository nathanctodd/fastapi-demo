# Lab 6


## Discussion Questions:
1. What base image does the Dockerfile use?
    - The Dockerfile uses the `python:3.9-slim` base image, which is a lightweight version of Python 3.9.
2. How many services are defined in docker-compose.yml? What are their names?
    - There are two services defined in the `docker-compose.yml` file: `fastapi` and `mongodb`.
3. Which port does FastAPI listen on inside the container, and which host port is it mapped to?
    - FastAPI listens on port 8000 inside the container, and it is mapped to port 8000 on the host machine.
4. What environment variable tells FastAPI where to find MongoDB?
    - The environment variable `MONGO_URL` tells FastAPI where to find MongoDB. It is set to `mongodb://mongodb:27017/`, which indicates that MongoDB is running in a container named `mongodb` on the default port 27017.
5. What do insert-one.py and insert-many.py do?
    - `insert-one.py` is a script that inserts a single document into the MongoDB collection. It creates a dictionary with some data and uses the `insert_one` method to add it to the collection.
    - `insert-many.py` is a script that inserts multiple documents into the MongoDB collection. It creates a list of dictionaries, each representing a document, and uses the `insert_many` method to add them to the collection.

## Resource Stats
1. Which container uses more memory at idle - FastAPI or MongoDB?
    - At idle, the fast api contain user 3% more memory than the MongoDB container. This is likely because FastAPI is running a Python application, which may require more resources than the MongoDB database when it is not actively handling requests.
2. What is the MEM USAGE / LIMIT ratio for each?
    - FASTAPI: 6.86% (269.2MiB / 3.826GiB)
    - MongoDB: 0.5% (125.1MiB / 3.828GiB)