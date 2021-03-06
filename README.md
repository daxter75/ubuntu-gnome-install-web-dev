# ubuntu-gnome-install-web-dev
Install Ubuntu GNOME 16.04 LTS for web dev

-----
Download latest version of [Ubuntu GNOME][uglink] (ISO file)

Burn this ISO to DVD or create a bootable USB drive (you can use [UNetbootin][unblink])
    
Ubuntu GNOME can work as single OS or you can use dual boot (with Windows OS).

Install Ubuntu GNOME (before installation: you can try Ubuntu GNOME without affecting your current OS installation - just click on "Try Ubuntu" option)

Optional: Setup partition (swap partition should be double sized compared to RAM)

Confirm: install third-party software

Set: timezone, keyboard layout, name, computer name, password and select “require password to login”

Setup UEFI (motherboard bios) - if needed

After OS installation, log in, run terminal window and type: 

    sudo apt-get update

(use this command before every installation)

Notice: text in square brackets you need to change with your data

# Apache

    sudo apt-get install apache2

# MySQL and PHP

    sudo apt-get install mysql-server php7.0-mysql

    mysql_secure_instalation   (TODO > wait for questions and type: n;n;y;y;y;y)

    service mysql status

    sudo apt-get install php libapache2-mod-php

    sudo nano /var/www/html/info.php (TODO > make file with phpinfo() function)

    sudo service apache2 restart

Type in browser: localhost/info.php

Check: 

    php -v

    mysql -V


# phpMyAdmin

    sudo apt-get install phpmyadmin php-mbstring php-gettext (TODO > apache2, yes, [password])

    sudo phpenmod mcrypt

    sudo phpenmod mbstring

    sudo nano /etc/apache2/apache2.conf (add line: Include /etc/phpmyadmin/apache.conf)

    sudo service apache2 restart

# Change folder owner

    sudo chown -v [user] /var/www/html/

    sudo chmod -R 755 /var/www/html/

(for [user] type your linux username)

# Chrome
Download a 64bit .deb file

    sudo dpkg -i /path/to/chrome/file

if error occur, type: 

    sudo apt-get -f install

    sudo dpkg -i /path/to/chrome/file

Google killed 32bit version Chrome for Linux. You can install 32bit Chromium: 
    
    sudo apt-get install chromium-browser

# Git

    sudo apt-get install git

    git config --global user.name “[username]”

    git config --global user.email “[username@domain]”

    git config --global push.default simple

    git config --list

# Composer

    sudo apt-get install curl

    curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

Check:

    composer -v (display version)

# MySQL Workbench

    sudo apt-get install mysql-workbench

# Editors
You can install free IDE like NetBeans or Eclipse, purchase a PhpStorm, or something of your preference.

# Advice
Be patient! :)

# Credits:
http://ddujin.com

https://wiki.ubuntu.com

http://askubuntu.com

https://www.digitalocean.com

[uglink]: <https://ubuntugnome.org/>
[unblink]: <https://unetbootin.github.io/>
