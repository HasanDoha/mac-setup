### Laravel Installation

### Step#1: Install Composer

Run this in your terminal to get the latest Composer version:

$ php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

$ php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

$ php composer-setup.php

$php -r "unlink('composer-setup.php');"

$ mv composer.phar /usr/local/bin/composer

If the above fails due to permissions, you may need to run it again with sudo. On some versions of OSX the /usr directory does not exist by default. If you receive the error "/usr/local/bin/composer: No such file or directory" then you must create the directory manually before proceeding:

$ mkdir -p /usr/local/bin.

### Step#3: Install Laravel

$ composer global require "laravel/installer"

test the installation using following command

$ laravel new blog

### Step#3: Install Valet

Run the following commands

$ brew update

$ brew install homebrew/php/php71

$ composer global require laravel/valet

Then add ~/.composer/vendor/bin directory is in your system's "PATH" using following commands...

$ echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.bash_profile

$ source ~/.bash_profile

Then run

$ valet install

to install MySQL

$ brew install mysql

to start MySQL

$ brew services start mysql

Create a new directory on your Mac by running something like...

$ mkdir ~/Sites

Next,

$ cd ~/Sites

and run

$ valet park

Next, create a new Laravel site within this directory:

$ laravel new blog

Open http://blog.dev in your browser
