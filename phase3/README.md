# Phase3: Database Server setup
We will use the MariaDB database engine, a community-developed open-source fork of MySQL, to support our relational databases backing.

## Installation
Install with the package manager. Now the mariadb engine is packaged by the name `mariadb-server` in the dnf package repository 
- Install with command

        sudo dnf install mariadb-server -y
- Start the mariadb server with terminal command

        sudo systemctl start mariadb

- By default, the server will only be starting when you explicity tell the server to start. To have enable the server start on systemboot with command
        
        sudo systemctl enable mariadb

- And check the status for the server with command

        sudo systemctl status mariadb


- To install database securely on your linux server, type in command

        mysql_secure_installation

- Press `Enter` for first installation and `Y` for setting up a new password
- Set a root password for the mysql database
- Leave everything else on defaults
    - To deny anonymous users
    - Disallow root login remotely
    - Remove test database and access to it
    - Reload privileges


- Finally login to your freshly installed mariadb-server with command

        - mysql -u root -p
-    `Enter your database root password` after the execution of command



## Optional
You can create and configure your own databases inside the MariaDB server, create your own users, tables and even configure control access. Always remember to flush privileges post the user configuration to ensure all changes take place effectively
-   Some basic commands you could try out to familiarize and get started
        
           show databases;
            use mysql;
            show tables;

## Completion
That’s it. Your MariaDB server is up and running!

## [Got o Phase4: PHP Server setup](../phase4/README.md)