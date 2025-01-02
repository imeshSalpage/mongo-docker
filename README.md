
# MongoDB Docker Setup

This repository provides a streamlined approach to deploying MongoDB using Docker, facilitating efficient database management and integration.

## Prerequisites

- Ensure that [Docker](https://docs.docker.com/get-docker/) is installed on your system.

## Setup Instructions

1. **Clone the Repository**:

   Begin by cloning this repository to your local machine:

   ```bash
   git clone https://github.com/imeshSalpage/mongo-docker.git
   cd mongo-docker
   ```

2. **Configure Environment Variables**:

   Duplicate the sample environment variable files to create active configuration files:

   ```bash
   cp tmp.mongo.env mongo.env
   cp tmp.mongo-express.env mongo-express.env
   ```

   Modify the `.env` files as necessary to suit your environment and preferences.

3. **Manage the Docker Environment**:

   - **Start the Services**:

     Utilize the `make` command to launch the MongoDB and associated services:

     ```bash
     make up
     ```

     This command initializes the Docker containers as defined in the `docker-compose.yml` file.

   - **Stop the Services**:

     To halt the running services, execute:

     ```bash
     make down
     ```

   - **Additional Commands**:

     For other operations, refer to the `Makefile` included in this repository, which contains various commands for managing the Docker environment.

## Accessing MongoDB and Mongo-Express

- **MongoDB**:

  Once the services are up, MongoDB will be accessible at `localhost:27017`.

- **Mongo-Express**:

  The Mongo-Express web interface can be accessed via `http://localhost:8081`, providing a user-friendly way to interact with your MongoDB instance.

## Customization

- **Environment Variables**:

  The `.env` files allow you to customize settings such as database credentials, ports, and other configurations. Ensure these files are correctly set up before starting the services.

- **Docker Compose Configuration**:

  The `docker-compose.yml` file defines the services, networks, and volumes. Modify this file if you need to change the default setup.

## Troubleshooting

- **Logs**:

  To view the logs for the running services, use:

  ```bash
  docker-compose logs
  ```

- **Shell Access**:

  To access the shell inside the MongoDB container:

  ```bash
  docker exec -it mongo-docker_mongo_1 bash
  ```

  Replace `mongo-docker_mongo_1` with the actual container name if it differs.

## Contributing

Contributions are welcome! Please fork this repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

For more information on using MongoDB with Docker, refer to the [official MongoDB Docker image documentation](https://hub.docker.com/_/mongo).
