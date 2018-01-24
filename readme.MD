# Linux Server Configuration Project

This readme displays information useful for grading the linux server configuration project in Udacity's Full Stack Web Dev Nanodegree.

## Server access
The server is accessible through SSH, using port 2200. The IP address is 18.218.133.130, and the user created for grading is 'grader'.
The URL used for access is: http://18.218.133.130/

## Software used
These were the software installed in the linux machine in order to get things working:

```
libapache2-mod-wsgi-py3
postgreSQL
pgloader
pip
```

Python Packages installed:

```
Flask==0.12.2
Flask-HTTPAuth==3.2.3
oauth2client==4.1.2
requests==0.4.2
psycopg2==2.7.3.2
SQLAlchemy==1.2.1
```

## Configuration

### Server

- The port listened from SSH was changed from 22 to 2200 for security measures. Remote root login was disabled.
- Firewall was configure to only allow incoming access from ports 80, 123 and 2200.
- A user (called 'grader') was created and granted sudo permissions, according to the project rubric. A public/private key pair was generated and made available for the user.
- Password was disabled, with the only method for authentication being a public-key.

### Database

- A database called myvinyls was created in PostgreSQL, and a user called Catalog was created and then granted limited access to the database.
- The former database file, from the application, was in SQLite format and thus was converted using the software pgloader into the myvinyls db in psql.

### Application

- The application ItemCatalog was cloned from github using git.
- The changes needed were made in the project in order to listen to the new postgres database.
- A WSGI file was created in the /var/www/filecatalog folder, in order to serve the application through apache and configured like so.

## Remarks

Thanks Udacity for the great course.
