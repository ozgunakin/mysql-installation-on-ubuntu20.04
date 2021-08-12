# MySQL Installation on Ubuntu 20.04

This is a step by step guide for MySQL installation on Ubuntu 20.04

## Step - 1 Install MySQL via APT

You can directly install MySQL using APT package manager. It is better to update the server before run "apt install" code.

```text
sudo apt update

sudo apt install mysql-server

sudo service mysql start

sudo systemctl enable mysql
```

## Step - 2 Security Settings

After installing MySQL with default settings, we will make the settings to increase the security of MySQL server.

```text
sudo mysql_secure_installation
```

After running this code, please follow the instructions shown on your terminal. After answer the question you will need to set root passport.

## Step - 3 Create an Admin User

We will create an admin user and give grant access to MySQL. 

* [x] Open MySQL on Terminal.

```text
sudo mysql
```

* [x] Create a user with a username and password. \(In MySQL, when you create a user you need to dedicate a hostname/IP to the user. When you do that, user can only access MySQL from this IP address. If you want to create a global user, you need to switch "localhost" with "%"\)

```text
CREATE USER 'adminuser'@'localhost' IDENTIFIED BY 'PASSWORD';
```

* [x] Authorize the user.

```text
GRANT ALL PRIVILEGES ON *.* TO 'adminuser'@'localhost' WITH GRANT OPTION;
```

* [x] Exit

```text
exit
```

* [x] Try to open MySQL using the credentials of the new user.

```text
mysql -u adminuser -p
```



