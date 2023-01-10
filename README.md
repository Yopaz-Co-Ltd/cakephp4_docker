# Development environment

## Version

PHP 8.1.16
Nginx 1.20.0
MySQL 8.0

## Environment

1. First of all, you need install docker desktop in this link: https://www.docker.com/products/docker-desktop/.
2. Make sure you can use the Docker command.
3. Clone this project
    ```bash
    git clone https://github.com/Yopaz-Co-Ltd/cakephp4_docker.git
    ```
4.
    ```bash
    cd cakephp4_docker
    ```
5. Build environment
   ```bash
   docker-compose up -d --build
   ```
6. Clone your project into folder workspace/cakephp4 with command:
   ```bash
   git clone link_your_project workspace/cakephp4
   ```
7. Connect to DB with info:
   (host: mysql, user: root, password: password, database name: cakephp4, database test name: db_test)
8. http://localhost:8765/