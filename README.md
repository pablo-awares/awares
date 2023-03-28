# awares

Odoo needs a PostgreSQL server to work with. The typical development setup is to have
PostgreSQL installed on the same machine as Odoo.
To install the PostgreSQL database on your Debian/Ubuntu system, run the following
commands:

```c++
sudo apt update
sudo apt install postgresql # Installs PostgreSQL
sudo su -c "createuser -s $USER" postgres 
```

To manually start the PostgreSQL service, run the following command:

```c++
sudo service postgresql start
```

## Installing the Odoo system dependencies

Odoo requires some system libraries to run. Git is needed to get the version-controlled
source code, and Python 3.6 or later is needed to run Odoo 13. The following are the basic
system dependencies that are needed:

```c++
sudo apt update
sudo apt upgrade
sudo apt install git # Install Git
sudo apt install python3-dev python3-pip python3-wheel python3-venv
sudo apt install build-essential libpq-dev libxslt-dev libzip-dev libldap2-dev libsasl2-dev libssl-dev
```
Ensure that the Python version is 3.9
```c++
python3 --version
```

## Clone the repository
Create a folder in the root called 'code':
```c++
/home/root/user_name/code
```

Then go inside the folder:
```c++
cd code
```

And clone the repository
```c++
git clone https://github.com/pablo-awares/awares.git
```

## Python environment
Next, we should install the Python dependencies that are declared in the
requirements.txt file. The recommended approach is to do this inside a Python
virtual environment. Doing so protects your Odoo environment from possible changes
in the system-wide Python libraries. Another benefit is to be able to keep several virtual
environments, according to the particular needs of the projects you are working on, such
as using older versions of Odoo. Let's get started:

```c++
python3 -m venv ~/code/env16
```
*env16 because odoo is version 16

Now we can activate the environment
```c++
source ~/code/env16/bin/activate
```

Check that (env16) appears at the beginning.

```c++
(env16) which python
/home/user_name/code/env16/bin/python
```

## Installing python dependencies
```c++
(env16)  pip install -U pip
(env16)  pip install -r ~/code/odoo/requirements.txt
```
## Installing odoo
```c++
pip install -e ~/code/odoo
```

## Running odoo
Check that the version is 16.0
```c++
source ~/code/env16/bin/activate
(env16) odoo --version
```

Now we can run odoo
```c++
(env16) odoo
```

To verify that everything is correct access to:
```c++
http://localhost:8069
```

## First time running odoo
The first time you need to create a new database
Access here:
```c++
http://localhost:8069
```

As you can see the master password is already defined, copy it, you could use it later.
Then fill every field with your data



