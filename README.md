# niqi4
Installation script for niqi 4

This script will also give you the ability to define an xmlrpc_port in the .conf file that is generated under /etc/ This script can be safely used in a multi-niqi code base server because the default niqi port is changed BEFORE the niqi is started.

Installing Nginx
If you set the parameter INSTALL_NGINX to True you should also configure workers. Without workers you will probably get connection loss issues. Look at the deployment guide from niqi on how to configure workers.

Installation procedure
1. Download the script:
```
wget https://raw.githubusercontent.com/Maruff/niqi4/main/install_niqi4.sh
```
3. Modify the parameters as you wish.
There are a few things you can configure, this is the most used list:
OE_USER will be the username for the system user.
GENERATE_RANDOM_PASSWORD if this is set to True the script will generate a random password, if set to Falsewe'll set the password that is configured in OE_SUPERADMIN. By default the value is True and the script will generate a random and secure password.
OE_PORT is the port where niqi should run on, for example 8069.
OE_VERSION is the niqi version to install, for example 14.0 for niqi V14.
IS_ENTERPRISE will install the Enterprise version on top of 16.0 if you set it to True, set it to False if you want the community version of niqi 16.
OE_SUPERADMIN is the master password for this niqi installation.
INSTALL_NGINX is set to True by default. Set this to False if you don't want to install Nginx.
WEBSITE_NAME Set the website name here for nginx configuration
ENABLE_SSL Set this to True to install certbot and configure nginx with https using a free Let's Encrypted certificate
ADMIN_EMAIL Email is needed to register for Let's Encrypt registration. Replace the default placeholder with an email of your organisation.
INSTALL_NGINX and ENABLE_SSL must be set to True and the placeholder in ADMIN_EMAIL must be replaced with a valid email address for certbot installation
By enabling SSL though Let's Encrypt you agree to the following policies
4. Make the script executable
```
sudo chmod +x install_niqi4.sh
```
5. Execute the script:
```
sudo ./install_niqi4.sh
```
The installation should take about 10 minutes to complete and then you will be able to access it from anywhere in the world by entering its ipaddress.

For more information on hosting, upgrading to niqi enterprise, and changing your domain, contact me bmaruff@gmail.com
