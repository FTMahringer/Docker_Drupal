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
git clone https://github.com/FTMahringer/Docker_Drupal.git
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
- PHPmyadmin user: root
- PHPmyadmin password: drupal_root

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

This is a part from the `docker-compose.yml`, the drupal volume:
```
    volumes:
      - ./drupalData/web:/var/www/html
    # alternate volume for when the above not working
    #volumes:
      #- /var/www/html
```
If the "normal" way doenst work for you:
1. Delete the drupaldata folder, that comes with the repo.
2. use the outcommented part and comment out the normal volume.
3. Build and start like normal
4. In the terminal, you can use this command, to get the drupal files from the container to a local:

To Display all containers:
```sh
docker ps  
```
there the CONTAINER IDs are displayed (they are what we want)

it looks like this:

![image](https://github.com/user-attachments/assets/e31b8c9b-7b62-4881-a236-d610e57c57c7)


to copy the container files into a local folder use:
```sh
docker cp (your Drupal container ID)/opt/drupal/ ./drupalData
```
The command looks lke this:

![image](https://github.com/user-attachments/assets/2d64ea6a-a4ca-4ceb-adc4-6ea210d2dfb9)

5. When that is done, go back to how the docker-compose was in its original state (if you do not, your local files will be ignored)

Hope this works for you.
