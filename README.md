# Docker_Drupal

This repository contains a Docker Compose setup for running a local Drupal environment with pre-configured Drupal files.

## Introduction
This repository contains the Docker setup for running a Drupal instance. It includes all necessary configurations to get a Drupal application up and running in a Docker environment.

## Prerequisites
- Docker
- Docker Compose

## Setup

### Clone the Repository
```sh
git clone https://github.com/FTMahringer/SAMC_Drupal-Docker.git
cd SAMC_Drupal-Docker
```

### Build and Start the Container
```sh
docker-compose up --build
```

### Accessing the Drupal Site
Once the containers are up and running, you can access the Drupal site at `http://localhost:8080`.

You can access the phpmyadmin at `http://localhost:8081`.

## Project Structure
- `docker-compose.yml`: Docker Compose configuration file.
- `drupalData/`: Contains the Drupal application data.
- `data/`: Contains the mariadb files.

### Configuration
The following environment variables are used in the Docker setup:
- DRUPAL_DB_USER: root
- DRUPAL_DB_PASSWORD: drupal_root
- DRUPAL_DB_HOST: mariadb
- Drupal User Credentials
- Username: admin
- Password: admin


## Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes.

## License
This project is licensed under the [MIT License](LICENSE).

## Contact
For any inquiries, please contact [FTMahringer](https://github.com/FTMahringer).


## Workaround

If this doesnt work for you, you can do also do it like this:

1. Use the alternate docker-compose.yml
2. Build and start like normal.
3. In the terminal, you can use this command, to get the drupal files from the container to a local:

To Display all containers:
```sh
docker ps  
```
there the CONTAINER IDs are displayed (they are what we want)

to copy the container files into a local folder use:
```sh
docker cp (your Drupal container ID)/opt/Drupal/ (your folder where it should be f.e.)./drupalData
```

now you can change back to the "original docker-compose" if you dont do that, then the local files will be ignored.
