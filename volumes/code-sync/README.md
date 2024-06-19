# Volumes: Code Synchronization
This project provides a practical example of the use of Docker volumes to optimize the development and delivery of containerized applications.

Differing from the conventional approach to data persistence, the technique adopted in this project uses Docker volumes strategically to perform real-time synchronization of applications within the container, eliminating the need to rebuild the image with each code update.

This method not only reduces development time, but also establishes an isolated and stable environment, promoting a continuous approach in the application development and delivery cycle.

## Summary of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)

## Installation
### Prerequisites
To ensure that the project works correctly, it is essential that **Docker** and **Docker Compose** are installed on your machine.

### Installation command
```bash
# Clone the repository
git clone https://github.com/LiviaKarolayne/Docker.git

# Change to the project directory
cd Docker-SamplesHub
```

## Usage
Here is a basic example of how to use this project:

```bash
# Change to the project directory
cd volumes/code-sync

# Perform a Compose environment initialization
docker-compose up -d

# Send an HTTP request to the application
curl localhost:5000

# Modify the application content
sed -i 's/Hello, World!/Testando Code-Sync/g' app.py

# Make sure the change has been applied
curl localhost:5000
```
#### Expected result
In this example, after initializing the Compose environment in which the application is hosted, when making the first request, the original snippet containing the message "Hello, World!" was obtained. With the modifications in the code, the application was updated internally in the container, starting to respond with "Testing Code-Sync" for the same request.

![Expected result](./doc/test_code_sync.png)

## Project Structure
The project follows a simple directory structure, organizing the main artifacts and files as follows:
```text
├── doc/
├── app.py
├── docker-compose.yml
├── Dockerfile
├── README.md
└── requirements.txt
└── requirements.txt
```

#### Directories Explanation
- `doc/`: Additional documentation about the project.
- `app.py`: Contains the main source code of a minimal Flask application.
- `docker-compose.yml`: Docker Compose configuration file, used to define Docker images.
- `Dockerfile`: Simple Dockerfile for creating an image intended for production environments.
- `README.md`: This file provides an overview of the project, instructions, and important information.
- `requirements.txt`: File that lists the dependencies required for the minimal Flask application.


