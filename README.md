# Data-Base
# Step 1 — Installing Docker
The Docker installation package available in the official Ubuntu repository may not be the latest version. To ensure we get the latest version, we’ll install Docker from official Docker repository. To do that, we’ll add a new package source, add the GPG key from Docker to ensure the downloads are valid, and then install the package.
### First, update your existing list of packages:
sudo apt update
### Next, install a few prerequisite packages which let apt use packages over HTTPS:
sudo apt install apt-transport-https ca-certificates curl software-properties-common
### Then add the GPG key for the official Docker repository to your system:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
### Add the Docker repository to APT sources:
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
This will also update our package database with the Docker packages from the newly added repo.

Make sure you are about to install from the Docker repo instead of the default Ubuntu repo:
apt-cache policy docker-ce
### Finally, install Docker:
sudo apt install docker-ce
### Docker should now be installed, the daemon started, and the process enabled to start on boot. Check that it’s running:
 sudo systemctl status docker
# Install mariadb and creating container:
1. start the dockerd daemon: sudo systemctl start docker sudo gpasswd -a "${USER}" docker
2. Download a MariaDB image for Docker: docker search mariadb
3. Create a container for the official MariaDB image: docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb:10.3
4. We can get a list of running containers in this way: docker ps We should get an output similar to this one:
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES 819b786a8b48 mariadb "/docker-entrypoint. 
5. To Restart a Container: docker restart mariadbtest
### connect mariadb container using below command.
sudo docker exec -it <container name> bash
### login to mariadb using below command.
sudo mysql -u root -p Enter passward : <provide root passward >
### Create database:
create database <database_name>;
### To list of database :
show databases;
### To connect database.
use <database_name>;
### Create table.
create table <table_name> ( coloumn name);
### Insert value in the table using below command.
insert into <table_name> (column1 ,column2, column3,column4.......) values (val1, val2, val3, val4.........);
### Show data of the table.
 select * from <table_name>;

  

