# Docker_Drupal

This repository contains a Docker Compose setup for running a local Drupal environment with pre-configured Drupal files.

## Project Description
This project aims to provide a ready-to-use local development environment for Drupal using Docker.

## Setup Instructions
1. Clone this repository:
   ```sh
   git clone https://github.com/FTMahringer/Docker_Drupal.git
   cd Docker_Drupal
   ```
Start the Docker containers:

   ```sh
docker-compose up -d
   ```
Access the Drupal site:

Drupal site: http://localhost:8080
phpMyAdmin: http://localhost:8081
### Configuration
The following environment variables are used in the Docker setup:

DRUPAL_DB_USER: root
DRUPAL_DB_PASSWORD: drupal_root
DRUPAL_DB_HOST: mariadb
Drupal User Credentials
Username: admin
Password: admin
### Usage Instructions
Access the Drupal site at http://localhost:8080
Use phpMyAdmin for database management at http://localhost:8081
### Contributing
Contributions are welcome! Please see the Contributing Guide for more details.

##License
This project is licensed under the MIT License - see the LICENSE file for details.
