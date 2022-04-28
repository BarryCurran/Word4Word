# Word4Word

This repository is Flask application for a Word4Word game. The application provides a 8 charcater or more word (the 'sourceword') from a dictionary and the user has to enter 7 guesses which are atleast 4 charcaters long from the 'sourceword'.

# Get the Sample Code

Create a GitHub account. Download and install git. We will use git to manage our source code. Fork this repository and clone your forked repository to your local machine.

# Setup the Project
### Create a Python 3 virtual environment:
python3 -m venv project-venv
source project-venv/bin/activate
### Install the required packages:
cd cyber-students
pip3 install -r requirements.txt

# Database Schema
### Download, install and start MariaDB Community Edition. We will use MariaDB as our database:
Open a MariaDB shell.
### Create a MariaDB Database called worddictionaryDB:
create database worddictionaryDB;
### Create an Admin User Account for the Database:
grant all on worddictionaryDB.* to ‘gameadmin’@’localhost’ identified by ‘password’;
### Log Out of MariaDB Shell:
quit
### Log in as the worddictionaryDB Admin:
mysql -u gameadmin -p worddictionaryDB
Enter Password: password
### Verify worddictionaryDB has no Tables:
show tables;
### Create a dictionary table:
create table dictionary (
	id int not null auto_increment primary key, 
	word varchar(64) not null 
) ; 
### Create Leaderboard table:
create table leaderboard (
	id int not null auto_increment primary key,
	position int not null,
	time float not null, 
	who varchar(64) not null, 
	sourceword varchar(64) not null, 
	matches varchar(256) not null
	) ;

