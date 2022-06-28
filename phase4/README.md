# Phase 4: PHP Server Module
We will be installing PHP, a general-purpose scripting language geared toward web development. While you can install any version of PHP, MySQL extension support has been depreciated below version 7.0. Thus, this phase will guide you onto the installation for version 7.4, just above the baseline where the installation commands would be similar even with the latest ones.

## Installation
Install with the package manager. The PHP server module is packaged by the name `php` in the dnf package repository. We will also enable a supplementary dependency `php-fpm` as an efficient method to minimize the memory consumption and raise the performance even when experiencing heavy traffic.
- List the version modules available with command

        sudo dnf module list php 
- Enable the module

        sudo dnf module enable php:7.4
- Install with command

        sudo dnf install php
- Check the version for your php 

        sudo php -v

This should be enough for beginner-level PHP installation as part of the LAMP server. But you can improve its efficiency with the `php-fpm` module, which was installed in the backgorund as a dependency.

To optimize your php module 
- Start `php-fpm` module

        sudo systemctl start php-fpm 
- Enable `php-fpm` module to start with boot order

        sudo systemctl enable php-fpm

- Resart to save configuration

        sudo systemctl restart httpd php-fpm

## Completion
That’s it. Your PHP server module is up and running!

## [Go to Phase5: Conclusion](../phase5/README.md)
