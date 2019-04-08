Linux Server - Sports Item Catalog
==================================
This is a Linux Server running the Item Catalog application on Lightsail which can be accessed here http://54.188.72.253.xip.io

## Instructions for accessing Linux Server
i. IP address and SSH port for server access: 54.188.72.253:2200
ii. http://54.188.72.253
iii. Software installed apache2, postgresql
iv. Configuration changes
- Add SSH port 2200 to Lightsail Firewall (removed port 22 after ssh restart)
- Configure SSH port 2200, HTTP port 80, and NTP port 123 with UFW
- SSH config port change from 22 to 2200 in sshd_config, then restart ssh
- Create _grader_ user, give `sudo` permissions, and create SSH key pair for _grader_
- Date/Time is in UTC
- Update server with apt package manager
- Install apache2 ```sudo apt-get install apache2```
- Install mod_wsgi and configure for apache requests ```sudo apt-get install libapache2-mod-wsgi```
- Install postgresql ```sudo apt-get install postgresql```
- Install python-pip, sqlalchemy, psycopg2, requests, oauth2client
- Install git
- Configure PSQL with the appropriate database, user and privileges
- Configure apache2 with appropriate support for application
v. Third party resources
https://www.vultr.com/docs/how-to-configure-ufw-firewall-on-ubuntu-14-04
http://www.postgresqltutorial.com/postgresql-python/connect/
https://docs.sqlalchemy.org/en/latest/core/engines.html#postgresql

## API
The item catalog has a list of API endpoints available for use which return JSON.
### Examples
To access the list of Sports:
```http://localhost/sports/JSON```

To access all items of a specific sport:
```http://localhost/sport/<sport_id>/items/JSON```

To access a specific sports item of a sport:
```http://localhost/sport/<sport_id>/item/<sport_item_id>/JSON```
