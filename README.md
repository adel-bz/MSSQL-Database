# MSSQL-Config

# Table of Contents
- [Introduction](https://github.com/adel-bz/MSSQL-Config#introduction)
- [Configuration](https://github.com/adel-bz/MSSQL-Config#configuration)
- [Requirements](https://github.com/adel-bz/MSSQL-Config#requirements)
- [Usage](https://github.com/adel-bz/MSSQL-Config#usage)
- [Test](https://github.com/adel-bz/MSSQL-Config#test)
- [Refrences](https://github.com/adel-bz/MSSQL-Config#refrences)


# Introduction
Welcome to the MSSQL-Config project repository! This project aims to provide a convenient and standardized way to configure and manage Microsoft SQL Server instances with Docker.
I installed dependencies drivers for MSSQL on the container.
Also, I used Apache as a webserver and a PHP code (QuickDbTest.php) for testing MSSQL Database.

# Configuration
## API
API directory includes Apache configs as a webserver and a Dockerfile for installing MSSQL drivers to connect to the database.
You can use Nginx instead of Apache as a websever.

## DB
DB directory includes config files for creating and configuring Microsoft SQL Server.

If you want to change the database name you should change ```db_example``` on ```db/setup.sql``` to your database name. On top of that you should change ```private const db``` on ```QuickDbTest.php```  to your database name.

On the other hand, to change the database password, you should change ```private const pass ``` on ```QuickDbTest.php```  and ```SA_PASSWORD``` on ```docker-compose.yml```.

# Requirements
#### Step 1 
OS: Linux all versions (Ubuntu recommended).

#### Step 2 
Install [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04) and [docker-compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04) on your machine.

# Usage
## Clone project
```  
git clone https://github.com/adel-bz/MSSQL-Config.git
```
## Run project
```
cd MSSQL-Config
sudo bash launcher.sh
```
## Stop project
```
sudo docker-compose down -v
```

# Test
Write the below address on your browser:
```
http://127.0.0.1:4567/QuickDbTest.php
```
Or use the below command on your terminal:
```
curl http://127.0.0.1:4567/QuickDbTest.php
```
You must get a response like this:
```
<pre>
[
    {
        "congratulations": "Success!!!",
        "stars": "1"
    },
    {
        "congratulations": "You did it!!!",
        "stars": "2"
    }
]</pre>
```

# Refrences
https://hub.docker.com/_/microsoft-mssql-server

https://gist.github.com/xenogew/3440d323b00e1d661966f2b2ca3ef64a

https://stackoverflow.com/questions/75631319/pecl-install-pdo-sqlsrv-make-fails-on-ddev-using-debian-11-missing-libltdl-la
