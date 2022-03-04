# Odoo_pycharm_set_up
Set up Odoo ERP using Pycharm


## Download Pycharm
### Or Open Terminal (you can use Ctrl + Alt + T to open terminal) and execute the following commands:

> sudo apt-get update 
> sudo apt-get upgrade
> sudo snap install pycharm-community --classic

 ## Install Python3 and necessary packages

We can install the Python3 using the following command:

> sudo apt-get install -y python3-pip

## The installation of the necessary packages for the Python3 can be done using the following code:

> sudo apt-get install python-dev python3-dev build-essential libjpeg-dev libpq-dev libjpeg8-dev libxml2-dev libssl-dev libffi-dev libmysqlclient-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev liblcms2-dev

## Install Web dependencies
Next, we have to install the web dependencies:
> sudo apt-get install -y npm
> 
> sudo ln -s /usr/bin/nodejs/usr/bin/node 
> 
> sudo npm install -g less less-plugin-clean-css 
> 
> sudo apt-get install -y node-less


 ## Install the Wkhtmltopdf
If you require to print reports that are generated in Odoo you need to install Wkhtmltopdfwhich can be done using the following code:
> sudo wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.bionic_amd64.deb 
> 
> sudo dpkg -i wkhtmltox_0.12.5-1.bionic_amd64.deb 
> 
> sudo apt install -f

## Install PostgreSQL
Next, we have to install PostgreSQL:

> sudo apt-get install postgresql

## Create a Database User Role for Handling Odoo Databases

> sudo su - postgres
> createuser --createdb --username postgres --no-createrole --no-superuser --pwprompt odoo14

## Make the defined user as a superuser
> psql
> ALTER USER odoo15 WITH SUPERUSER;

exit form sql and also Postgres User
> \q
> exit

## create project directory
> mkdir odoo_projects

> cd odoo_projects

## Make odoo directory as you may set up diffrent odoo version instances

> mkdir odoo-14


## Find out python virtual environments are on your machine

run 
> pyenv versions

## Create python virtual Environment

run 
> pyenv virtualenv 3.8.12 odoo-14-python-3.8.12

> cd odoo-14

## Pull Odoo 14 version form github with emphasis on a particular branch you are interested in

> git clone https://www.github.com/odoo/odoo --depth 1 --branch 14.0

## Install python packages required to run odoo
> pip install -r odoo/requirements.txt

> mkdir etc
> mkdir data

## Open Odoo Project in Pycharm
Open Pycharm Community and Open odoo15 directory

## Create odoo.conf File inside odoo15 Directory

Right-click on the directory -> New -> File -> odoo.conf

## Paste the following block into the file odoo.conf, and you should change the db_password, which is the password you set for the database user odoo15 in the earlier step.

> [options]
> ; Is This The Password That Allows Database Operations:
> admin_passwd = admin
> db_host = localhost
> db_port = 5432
> db_user = odoo15
> db_password = False
> addons_path = /home/user/odoo/addons
> xmlrpc_port = 8015


## Add Python Interpreter

Go to File -> Settings -> Project: odoo15 -> Python Interpreter

## Add configurations 

And Run Odoo form pycharm








