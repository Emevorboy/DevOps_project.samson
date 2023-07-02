
# WEB STACK IMPLEMENTATION (LEMP STACK)
## STEP 1 – INSTALLING THE NGINX WEB SERVER
Step 1 – Installing the Nginx Web Server
In order to display web pages to our site visitors, we are going to employ Nginx, a high-performance web server. We’ll use the apt package manager to install this package.

Since this is our first time using apt for this session, start off by updating your server’s package index. Following that, you can use apt install to get Nginx installed:
![Screenshotpjtest 2023-07-01 104609](https://github.com/Emevorboy/DevOps_project.samson/assets/103654905/a72a71e8-57d1-403d-a93b-61f401cdc450)



# STEP 2 — INSTALLING MYSQL
Now that you have a web server up and running, you need to install a Database Management System (DBMS) to be able to store and manage data for your site in a relational database. MySQL is a popular relational database management system used within PHP environments, so we will use it in our project.

![Screenshotsam2projectecho 2023-07-01 151521](https://github.com/Emevorboy/DevOps_project.samson/assets/103654905/a1741f2c-7005-424c-94e1-4e6b29dc33bb)

# STEP 3 – INSTALLING PHP
Step 3 – Installing PHP
You have Nginx installed to serve your content and MySQL installed to store and manage your data. Now you can install PHP to process code and generate dynamic content for the web server.

While Apache embeds the PHP interpreter in each request, Nginx requires an external program to handle PHP processing and act as a bridge between the PHP interpreter itself and the web server. This allows for a better overall performance in most PHP-based websites, but it requires additional configuration. You’ll need to install php-fpm, which stands for “PHP fastCGI process manager”, and tell Nginx to pass PHP requests to this software for processing. Additionally, you’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. Core PHP packages will automatically be installed as dependencies.

To install these 2 packages at once, run:

sudo apt install php-fpm php-mysql


# STEP 4 — CONFIGURING NGINX TO USE PHP PROCESSOR

Step 4 — Configuring Nginx to Use PHP Processor
When using the Nginx web server, we can create server blocks (similar to virtual hosts in Apache) to encapsulate configuration details and host more than one domain on a single server. In this guide, we will use projectLEMP as an example domain name.

On Ubuntu 20.04, Nginx has one server block enabled by default and is configured to serve documents out of a directory at /var/www/html. While this works well for a single site, it can become difficult to manage if you are hosting multiple sites. Instead of modifying /var/www/html, we’ll create a directory structure within /var/www for the your_domain website, leaving /var/www/html in place as the default directory to be served if a client request does not match any other sites.

Create the root web directory for your_domain as follows:

sudo mkdir /var/www/projectLEMP

![Screenshotsam2projectecho 2023-07-01 151521](https://github.com/Emevorboy/DevOps_project.samson/assets/103654905/c3a88135-03b5-4b1f-87ed-d6af9a6a99f8)

# STEP 5 – TESTING PHP WITH NGINX
Step 5 – Testing PHP with Nginx
Your LEMP stack should now be completely set up.

At this point, your LAMP stack is completely installed and fully operational.

You can test it to validate that Nginx can correctly hand .php files off to your PHP processor.

You can do this by creating a test PHP file in your document root. Open a new file called info.php within your document root in your text editor:

sudo nano /var/www/projectLEMP/info.php

![Screenshotsamprojectphp 2023-07-01 152030](https://github.com/Emevorboy/DevOps_project.samson/assets/103654905/9bc8de5f-a1b4-41c2-b71f-a85cf8ffb1f4)

# STEP 6 – RETRIEVING DATA FROM MYSQL DATABASE WITH PHP (CONTINUED)

Step 6 — Retrieving data from MySQL database with PHP
In this step you will create a test database (DB) with simple “To do list” and configure access to it, so the Nginx website would be able to query data from the DB and display it.

At the time of this writing, the native MySQL PHP library mysqlnd doesn’t support caching_sha2_authentication, the default authentication method for MySQL 8. We’ll need to create a new user with the mysql_native_password authentication method in order to be able to connect to the MySQL database from PHP.

We will create a database named example_database and a user named example_user, but you can replace these names with different values.

![Screenshotsamtodolist 2023-07-02 131356](https://github.com/Emevorboy/DevOps_project.samson/assets/103654905/7e545215-3f09-472d-b23c-078a35783356)
