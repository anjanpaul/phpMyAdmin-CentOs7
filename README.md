## 1. Install an Apache Web Server
The first prerequisite of phpMyAdmin is an Apache web server. Use the following command to install Apache on your CentOS 7 virtual private server:

```
yum install httpd -y

```

Next, check the status of apache with the command:

```
systemctl status httpd

```

Next, we should make sure that Apache is running. Enter your server’s IP address into a browser address bar. You should see the Apache testing splash screen:

![alt text](https://github.com/anjanpaul/phpMyAdmin-CentOs7/blob/main/output/apache-testing-spash-screen.jpeg)

## 2. Install the EPEL Repository

phpMyAdmin comes in the EPEL repository (Extra Packages for Enterprise Linux). To access EPEL you need to install a special package – epel-release. Use the following command to install epel-release on your CentOS:

```
sudo yum install epel-release

```
Now that the EPEL repo is made available, we can proceed to install phpMyAdmin on CentOS 7.

## 3. Install phpMyAdmin on CentOS 7

```
sudo yum install phpmyadmin

```

Once the installation is complete, you will have to edit the phpMyAdmin configuration file.

## 4. Configure the phpMyAdmin.conf File

The edit will make sure that you can access your phpMyAdmin client remotely. We’ll open the phpMyAdmin.conf file located in the directory /etc/httpd/conf.d/ using the vim editor:

```
vim /etc/httpd/conf.d/phpMyAdmin.conf

```

Here you will see four different require ip strings matched with long IPs. The default value is 127.0.0.1. Replace that value with the IP of the machine you will be using to access phpMyAdmin. You can use a tool like WhatsMyIP to check your IP. Save and exit the file by hitting escape and typing in :wq.

You can see an example of the phpMyAdmin.conf file below:

![alt text](https://github.com/anjanpaul/phpMyAdmin-CentOs7/blob/main/output/phpmyadmin-configuration-file.png)

## 5. Restart the Apache Web Server

Next we’ll restart the Apache web server by entering the following command in the command line:

```
systemctl restart httpd

```
## 6. Check if phpMyAdmin is Working

Finally, we can open phpMyAdmin utility by entering in your server’s IP address in a browser’s address bar with the addition /phpmyadmin string like so – 127.0.0.1/phpmyadmin. There you should see the login screen.

## 7. Locate Your phpMyAdmin Username and Password

Your username and password will be located in the file config.inc.php. The file will be in the phpMyAdmin installation directory. For us it is /etc/phpMyAdmin.

Open the file using the vim editor:

```
vim config.inc.php

```

Inside you can set the username and password, as shown in the screenshot below:

![alt text](https://github.com/anjanpaul/phpMyAdmin-CentOs7/blob/main/output/phpmyadmin-user-configuration-file.png)

Save and exit the file by hitting esc and :wq as before.

# Conclusion

That’s it, now you can log in! You have completed the phpMyAdmin install on CentOS 7.
