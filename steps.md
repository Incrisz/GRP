First you install python3

Also confirm pip is working fine

To create a virtual environment and install packages within it, you can follow these steps:

Install the virtualenv package (if not already installed):

=> pip install virtualenv

Create a new virtual environment:

=> virtualenv myenv

This command creates a new directory named myenv, which will contain the isolated environment.

Activate the virtual environment:

On Linux/macOS:

=> source myenv/bin/activate

On Windows (Command Prompt):

=> myenv\Scripts\activate.bat

or (PowerShell):

=> myenv\Scripts\Activate.ps1

Once activated, your command prompt or terminal should indicate that you are now using the virtual environment.

Install the packages within the virtual environment:

=> pip install -r cryptographic_requirements.txt

This command will install the packages listed in the cryptographic_requirements.txt file within the virtual environment.

By using a virtual environment, you can avoid potential conflicts and ensure that the project dependencies are isolated from the system-wide Python installation.

Also we need to get postgresql latest version and the pgadmin tool downloaded

To install the latest version of PostgreSQL and the pgAdmin tool, you can follow the steps below based on your operating system.

Ubuntu:

Add the PostgreSQL:

=> sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
=> wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
=> sudo apt-get update
=> sudo apt-get -y install postgresql


Install pgAdmin:

#
# Setup the repository
#

# Install the public key for the repository (if not done previously):
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg

# Create the repository configuration file:
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'

#
# Install pgAdmin
#

# Install for both desktop and web modes:
sudo apt install pgadmin4

# Install for desktop mode only:
sudo apt install pgadmin4-desktop

# Install for web mode only: 
sudo apt install pgadmin4-web 

# Configure the webserver, if you installed pgadmin4-web:
sudo /usr/pgadmin4/bin/setup-web.sh

During the installation, you will be prompted to set a password for the PostgreSQL database superuser (typically postgres). Remember this password as you will need it to access the database server.

macOS:

Install PostgreSQL and pgAdmin using Homebrew:

=> brew install postgresql pgadmin4

Homebrew will handle the installation and setup of both PostgreSQL and pgAdmin for you.

Windows:

Download the PostgreSQL installer from the official website:

Go to the PostgreSQL download page: https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
Choose the version appropriate for your system (e.g., Windows x86-64) and click the download link.
Run the downloaded installer executable.
Follow the installation wizard:

Select the components you want to install. Make sure to select the PostgreSQL server component.
Choose an installation directory.
Set the password for the database superuser (typically postgres). Remember this password.
Complete the installation.
Download the pgAdmin tool from the official website:

Go to the pgAdmin download page: https://www.pgadmin.org/download/pgadmin-4-windows/
Download the installer appropriate for your system (e.g., Windows, 64-bit).
Run the downloaded installer executable.
Follow the installation wizard for pgAdmin:

Choose an installation directory.
Complete the installation.
After completing the installation, you should have both PostgreSQL and pgAdmin installed on your system. You can launch pgAdmin to connect to your PostgreSQL database server and manage your databases.





