# Inception

This project is part of the 42 curriculum, focusing on building a small infrastructure using Docker. It includes services such as NGINX, WordPress, and MariaDB, each running in isolated Docker containers.

For detailed project requirements, please refer to the [subject PDF](https://github.com/your-username/inception/subject.pdf).

## Project Structure

```
.
├── Makefile
└── srcs
    ├── docker-compose.yml
    └── requirements
        ├── nginx
        │   ├── Dockerfile
        │   └── conf
        ├── wordpress
        │   └── Dockerfile
        ├── mariadb
        │   └── Dockerfile
        ├── redis (bonus)
        │   └── Dockerfile
        ├── ftp (bonus)
        │   └── Dockerfile
        ├── static_website (bonus)
        │   └── Dockerfile
        ├── adminer (bonus)
        │   └── Dockerfile
        └── custom_service (bonus)
            └── Dockerfile
```

## Mandatory Requirements

- All services run in separate Docker containers.
- Docker images are based on either Alpine or Debian (latest stable versions).
- NGINX uses TLSv1.2 or TLSv1.3 only.
- Volumes are set up for WordPress and MariaDB.
- Containers communicate via a Docker network.
- Configuration is managed using environment variables.
- Domain name follows the format: login.42.fr.

## Bonus Features

- Redis cache
- FTP server
- Static website (excluding PHP)
- Adminer
- Additional custom service

## Installation and Usage

1. Clone this repository:
   ```
   git clone https://github.com/tayou89/inception.git
   ```

2. Navigate to the project directory:
   ```
   cd inception
   ```

3. Set up a virtual machine (e.g., using VirtualBox).

4. Inside the virtual machine, set up the necessary environment variables. Create a srcs/.env file with the following content:
   ```
   DOMAIN_NAME=your-login.42.fr
   CERTS_=/path/to/your/certificates
   MYSQL_ROOT_PASSWORD=your_root_password
   MYSQL_USER=your_mysql_user
   MYSQL_PASSWORD=your_mysql_password
   # Add other required environment variables...
   ```

5. Build and run the project using the Makefile:
   ```
   make
   ```

## Important Notes

- This project must be run in a virtual machine environment.
- The .env file is not included in the git repository for security reasons. You must create it locally.
- Configure your domain name (your-login.42.fr) to point to your local IP address.

## Troubleshooting

If the `make` command doesn't work properly:
1. Ensure the .env file is correctly set up.
2. Verify that Docker and Docker Compose are installed in your virtual machine.
3. Check if the necessary ports (e.g., 443) are open.