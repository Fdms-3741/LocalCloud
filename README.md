# LocalCloud

A simple docker-compose.yml template, file structure and scripts that offers a container network of numerous web applications. The project aims to be of quick-setup, low maintenance and still with capacity for improvement.

The project assist people with low experience in docker container so that little to no configuration is nedded in the folders. Even so, it is assumed that the user is familiar (or at least confortable) to  concepts such as file permissions and tampering with configuration files to a minimum

## Planning

This project will contain these containers for essencial functionality:

| name | description | reason |
| --- | --- | --- |
| nginx | HTTPS server | Provides a site under a single secure domain to access all services |
| bind9 | DNS server | Provides an Authoritative DNS server to separate each service by name |
| postgresql | Database | Will be the main database for all applications that require |

The inital services will be as follow: 

| name | description |
| --- | --- |
| nextcloud | Personal cloud |
| portainer | Container management |

The main objective is to configure everything so that a user wanting to access any application would do so by just typing https://service.server-name. Those services will initialy be served only to localhost, but it is possible to open this services to the local network.

## Projects goals

* Configure Postgresql
	* Set initalization script that creates an user and database for each application

* Configure bind9
	* Configure main configuration file to set bind9 as an authoritative server
	* Find where the server-name is filled
	* Find how to add new services under the server-name domain

* Configure nginx
	* Set up to proxy by https with a self-signed certificate
	* Configure Fast-CGI (for nextcloud)
	* Set up each proxy for each application, separated by server name

* Verify if any configuration is required to nextcloud
* Verify if any configuration is required to portainer

* Provide step-by-step solution to add a new service

* Provide an script to execute the previous step-by-step


# How to use

The configuration files nedded to properly set the stack will be listed as the project progresses. See #Projects\_goals

Once all the configuration is done, this stack can be started by typing to the terminal 
```
sudo docker-compose up -d
```
