# Phase2: Apache Server setup
We will be installing an apache server on our previously built Linux machine. Apache is a web server software that is free, completely open-source, feature-rich, and simple enough as one of the most popular web servers on the market.

## Installation
- Connect to your Linux server with `ssh`
- Install with the package manager. Now the apache is packaged by the name `httpd` in the dnf package repository
- Install with command

        sudo dnf install httpd -y
- Start the apache server with command

        sudo systemctl start httpd
- By default, the server will only be starting when you explicity tell the server to start. To have enable the server start on systemboot with command

        sudo systemctl enable httpd
- And check the status for the server with command

        sudo systemctl status httpd

## Optional
You can edit your own web server by editing the index file in apache html directory. Editing can be done with vi text editor with command 
    
    sudo vi /var/www/html/index.html
Don't forget to restart your apache server post editing the index file 

    sudo systemctl restart httpd

## Completion
That’s it. Your Apache web server is up and running! Go to EC2 -> Instances -> Select the instance server machine -> Details -> Copy Public IPv4 DNS -> Paste in your local browser as `http://<Public IPv4 DNS>`



## [Go to Phase3: Database Server setup](../phase3/README.md)