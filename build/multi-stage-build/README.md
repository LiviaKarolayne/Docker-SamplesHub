# Build: Multi-stage Build
This project provides a practical example for production scenarios with disk space constraints. It also presents best practices for creating efficient production environments. The main approach adopted is the use of multi-stage builds to optimize production environments derived from Docker containers, resulting in images with significantly reduced sizes.

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

# Change to the repository directory
cd Docker-SamplesHub
```

## Usage
Here is a basic example of how to use this project:

```bash
# Change to the project directory
cd multi-stage-build

# Run the build of the images
docker-compose build

# Check the size of each image
docker images
```
#### Expected result
In this example, two Docker images were generated: one following a traditional approach and the other optimized using the Multi-stage build. This resulted in a notable space saving, achieving a 94% reduction in the size of the optimized image compared to the conventional approach.

![Expected result](./doc/docker_image_list.jpeg)

## Project Structure
The project follows a simple directory structure, organizing the main artifacts and files as follows:
```text
├── multi-stage-build/
│   ├── app.py
│   ├── doc/
│   │   └── docker_image_list.jpeg
│   ├── docker-compose.yml
│   ├── Dockerfile
│   ├── Dockerfile-multi-stage-build
│   ├── README.md
│   └── requirements.txt
```

#### Directories Explanation
- `multi-stage-build/`: Contains the main source code of the project
- `doc/`: Additional documentation about the project.
- `app.py`: Contains the main source code of a minimal Flask application.
- `docker-compose.yml`: Docker Compose configuration file, used to define Docker images.
- `Dockerfile`: Simple Dockerfile that implements a traditional approach to creating an image for production environments.
- `Dockerfile-multi-stage-build`: Additional Dockerfile that implements a "multi-stage build" approach, aiming to create an image optimized for production environments.
- `README.md`: This file provides an overview of the project, instructions and important information.
- `requirements.txt`: File that lists the dependencies required for the minimal Flask application.

