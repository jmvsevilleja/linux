# linux

Package source list
`/etc/apt/sources.list`

Update packages
`sudo apt-get update`

Upgrade packages
`sudo apt-get upgrade`

Manual package
`man apt-get`

Install finger
`sudo apt-get install finger`

Package Search
https://packages.ubuntu.com

# User

See user info
`finger username`

See all users info
`cat /etc/passwd`

Adding user
`sudo adduser student`

Changing password
`sudo passwd student`

Connecting to a user
`ssh student@127.0.0.1 -p 2222`

List of Sudoers
`/etc/sudoers`
#
Generating SSH
`ssh-keygen`

Restrict writing your private key
`chmod 400 [KEY_FILENAME]`

Connecting SSH user
`ssh -i [PATH_TO_PRIVATE_KEY] [USERNAME]@[EXTERNAL_IP_ADDRESS]`

Disable password base logins
`sudo nano /etc/ssh/sshd_config`

To disable tunneled clear text passwords, change to no here!

PasswordAuthentication no

`sudo service ssh restart`

# File Permissions

owner   group   everyone

rw-     r--     r--

r=4 w=2 x=1 -=0
all=7

`chmod 777 file/folder`

change owner
`chown user file`

change group
`chgrp root file`


# Firewall
check status
`sudo ufw status`

Deny incoming
`sudo ufw default deny incoming`

Allow outgoing
`sudo ufw default allow outgoing`

Allow ssh
`sudo ufw allow 2222/tcp`

Allow http server
`sudo ufw allow www`

Enable firewall
`sudo ufw enable`

# Apache

Installing Apache
`sudo apt-get install apache2`

`sudo apt-get install python3 libexpat1 apache2 apache2-utils ssl-cert -y`

Installing mod wsgi
`sudo apt-get install libapache2-mod-wsgi` python2
`sudo apt-get install libapache2-mod-wsgi-py3` python3

Configure WSGI module
`sudo nano /etc/apache2/sites-enabled/000-default.conf`

<VirtualHost *:80>
WSGIScriptAlias / /var/www/html/myapp.py
</VirtualHost>

Python Application
`sudo nano /var/www/html/myapp.py`
```php
def application(environ, start_response):
    status = '200 OK'
    output = 'Hello World!'

    response_headers = [('Content-type', 'text/plain'), ('Content-Length', str(len(output)))]
    start_response(status, response_headers)

    return [output]
```

Restart Apache
`sudo apache2ctl restart`

`sudo systemctl restart apache2`

Enable mod-wsgi
`sudo a2enconf wsgi`


# PostgreSQL

`sudo apt-get install postgresql`


