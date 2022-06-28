# Overview
# Phase1: Linux Server setup on AWS
We will be using an RHEL-based operating system for this repo project. The reason for choosing this specific distro would be its rock-solid stable deployment released after continuous testing by RHEL.

## Installation
-	`Login AWS portal` -> account ID or alias with your IAM-defined user credentials.
-	Go to `EC2 services` -> `Launch an instance`
-	Name your instance appropriately `AWS-LAMP.` 
-	Configure the `VPC`
    -	Either of your choices, if you have created one -> Select appropriate public subnet associations -> DHCP/DNS resolute -> Route table for internet gateway.
    -	Or leave it as default if you don’t have one created
-	Configure instance `AMI`
    -	`Red Hat Linux 8` or `Rocky Linux 8`
        - Rocky Linux 8 is a downstream rebuild of RHEL 8 and, as such, aligns with the RHEL 8 lifecycle. So most of the configurations would be the same if you choose either of them.
    -	I would go with Red Hat for this example, plus there is a free tier instance type available for support as beginner-friendly.
-	Choose instance type
    -	`t2.micro` -> would be sufficient for this project, but you are free to choose your own size flavor
- Create a `key-pair` -> to help connect to this instance. Save this key at a secure place as you won’t be able to connect without it
-	Configure network firewall security group settings
    - Create a new security group with an appropriate name
    -	`Allow HTTP` -> from anywhere -> 0.0.0.0/0
    -	`Allow HTTPS` -> from anywhere -> 0.0.0.0/0
    -	`Allow SSH` -> from `My IP` -> you don’t want anybody else apart from you to have any direct access to your server
-	Launch the instance.

## Connect 
-	Ensure the Instance state is on the running for a green signal on status checks.
-	Connect 
    -	GUI
        - Top right column button -> EC2 Instance Connect -> Connect
    -	Terminal
        - Type `ssh -i <key-pair.pem file> ec2-user@<public ipv4 address>` -> Accept the fingerprint -> Connect
- Once connected, update your system to the latest available patches
    - Type `sudo dnf upgrade -y`

## Completion
That’s it. Your Linux server is up and running!

### [Go to Phase 2: Apache Server setup ](phase2/README.md)

