# Microservices Project with Docker and Docker Compose

This project demonstrates a microservices architecture using Docker and Docker Compose. The system consists of multiple services, each containerized with its own Docker image, and orchestrated using Docker Compose.

## Services

### 1. Eureka Server

- **Container Name:** eureka-server1
- **Port:** 8761
- **Description:** Eureka Server for service discovery.

### 2. Gateway Server

- **Container Name:** gateway_server
- **Port:** 8889
- **Description:** Gateway server routing requests to microservices.
- **Dependencies:** Depends on Eureka Server.

### 3. Service Client

- **Container Name:** service_client
- **Port:** 8089
- **Description:** Microservice handling client-related functionalities.
- **Dependencies:** Depends on Eureka Server and MySQL database (mysql2).

### 4. Service Voiture

- **Container Name:** SERVICE_VOITURE
- **Port:** 8085
- **Description:** Microservice handling vehicle-related functionalities.
- **Dependencies:** Depends on Eureka Server and MySQL database (mysql2).

### 5. MySQL Database

- **Container Name:** mysql2
- **Port:** 3306
- **Description:** MySQL database serving both Service Client and Service Voiture.
- **Database Name:** mydatabase
- **Credentials:** Username - root, Password - root

## Usage

1. Ensure Docker and Docker Compose are installed on your machine.
2. Clone this repository.
3. Navigate to the project directory.

   ```bash
   cd <project_directory>
   ```

## Run the following command to start the services:

   ```bash
   docker-compose up
   ```
This will create containers for each microservice, the gateway, and the Eureka Server.

## Access the services through the following URLs:

- Eureka Server: http://localhost:8761
- Gateway Server: http://localhost:8889
- Service Client: http://localhost:8089
- Service Voiture: http://localhost:8085
## Testing
After the containers are running, test each microservice individually to ensure proper functionality.

* Run the ```docker compose up``` command :
![Architecture](/Demonstration/1.png)
* Check Docker Desktop to verify the creation of the container, or u can simply type ```docker ps ```to check the images that are currently running 
![Architecture](/Demonstration/4.png)
Now go check ```localhost:8761``` to see if everything is going smoothly, you must have this kind of interface:
![Architecture](/Demonstration/6.png)

To test :
![Architecture](/Demonstration/7.png)
![Architecture](/Demonstration/8.png)
![Architecture](/Demonstration/12.png)
Now the databases:
![Architecture](/Demonstration/10.png)
![Architecture](/Demonstration/11.png)


## Additional Information
- The `docker-compose.yml` file defines the services, their dependencies, and network configurations.
- Microservices are containerized using separate Dockerfiles in their respective directories.
* MySQL database volume is persistent across container restarts.












