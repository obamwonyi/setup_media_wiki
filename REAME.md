## Set Up Media Wiki for Development . 


### Requirements 
- see the [Requirement Url](https://www.mediawiki.org/wiki/Manual:Installation_requirements)
- **Also if you are on windows , use WSL**, not sure what this is 
read up on it [here](https://learn.microsoft.com/en-us/windows/wsl/install)

### Installation 
- Clone the repository as shown below 
    
    `git clone https://gerrit.wikimedia.org/r/mediawiki/core.git`

    Note it is advisable you clone the repo, as it offers more flexibility in development and setup. As well as keeping up with latest commits and so on. 
- You can also download the zip files or use curl or wget is you are on linux in the this link -> [zip/curl/wget](https://www.mediawiki.org/wiki/Download)

- Setup database: 
    - Install [MySQL](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04) or [MariaDB](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-22-04) 
    - Create User with password, will be used for setting up LocalSettings.php (more on this later).
        - ` CREATE USER 'your_user'@'localhost' IDENTIFIED BY 'your_password'; `

    - Create Database , will also be used for LocalSettings.php
        - ` CREATE DATABASE database_name ;`
    - Grant privileges to user(created above) on database(created above) 
        - `GRANT ALL PRIVILEGES ON database_name.* TO 'your_user'@'localhost';`
    

- Project Setup : 
    - Enter the root directory of the cloned MediaWiki project in the terminal, and run the command below :

    - ` composer install `

    after composer is done installing run this other command
    - ` npm install ` 

    please make sure you have npm installed if you don't have it, install it with [nvm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

    - Finally run the command below

    - ` php -S localhost:8080 `

    #### Note : you can use any port other than 8080 . as long as it's not occupied.

    - Click on the link provided in the terminal , you project would open on your default web browser, you would see a link on how to setup you project. This link will simply take you to a page where you can generate the LocalSettings.php file . 

    - Please make sure to fill in the database details from the database settings above correctly . 

    - After filling the details download the LocalSettings.php file and add it to the root of the project (MediWiki) directory and refresh the page or reserve the project


##### Comment below if you wan't me to make a setup with lamp stack on windows , with out the use of **WSL**. 
##### Fill free to also reach out to me if you have any issues, P.S. *Destiny Obamwonyi*