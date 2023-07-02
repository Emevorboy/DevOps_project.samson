
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

![Screenshotsamprojectphp 2023-07-01 152030](https://github.com/Emevorboy/DevOps_project.samson/assets/103654905/9bc8de5f-a1b4-41c2-b71f-a85cf8ffb1f4)
