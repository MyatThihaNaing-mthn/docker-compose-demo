# Containerizing a laravel app with nginx
A miminal setup for baisc laravel application with maria database 

##  🛠 ️Technologies used:
- Docker (Containerization)
- Docker-Compose (Container Orchestration)
- PHP FPM (PHP process manager)
- NGNIX (Reverse Proxy)
- Maria DB 
- PHPMyAdmin (Web base admin ui for RDMS)

## 🗂 ️Project Structure:
```
project-root/
├── code/
│   ├── app/                 # Laravel application
│   │   └── public/         # Public directory
│   └── phpinfo/            # PHP info directory
├── logs/
│   ├── mariadb/            # MariaDB logs
│   ├── nginx/              # Nginx logs
│   └── php/                # PHP logs
├── mariadb/
│   └── data/               # MariaDB data directory
├── nginx/
│   └── app_conf/           # Nginx configuration
│   │   └── demo.app.conf   # Site configuration
|   └──────nginx.conf       # Global nginx config
├── php_ini/
│   └── php.ini             # PHP configuration
├── docker-compose.yaml     # Docker compose configuration
├── nginx.dockerfile        # Nginx Dockerfile
├── php8.3-fpm.dockerfile   # PHP-FPM Dockerfile (base image for app)
└── php-node.dockerfile     # PHP-Node Dockerfile (for js and npm related ops such as installing dependencies and building project)
```

## 📖 Descriptions

- code/  
    serves public files from public folder and php files are executed by the application server based on the request 

- logs/  
     for logging purpose 

- maridb/  
    persistance layer 

- php_ini/  
    php configuration

- docker-compose.yaml  
    Yaml file config for managing all containers required for the application

- nginx/ php8.3-fpm/ php-node  
    Docker file for creating respective image


## 🌐  Nginx Server
- Nginx server will listen for the request on port 80 and 443 for http and https respectively

- It will serve the static files directly otherwise forwards the requests to the application server which is listening on port 9000


## ▶️ How to run the project

1. Clone the repository:
```bash
    git clone 
    [https://github.com/sannkoko/laravel_docker_compose.git]
    cd laravel_docker_compose
```
2. Build the images
```bash
    docker compose build
```
3. Start the containers
```bash
    docker compose up -d
```
4. Access the laravel app at http://localhost

5. Access the phpMyAdmin at http://localhost:8080

6. Stop the application
```bash
    docker compose down
```

