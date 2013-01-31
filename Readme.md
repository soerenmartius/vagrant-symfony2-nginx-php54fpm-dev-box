Vagrant Symfony2 Development box with Nginx and PHP 5.4
===============================================

Installation
------------

### this box is only tested with ubuntu precise 64 bit

* Install vagrant using the installation instructions in the [Getting Started document](http://vagrantup.com/v1/docs/getting-started/index.html)
* Add a Ubuntu Precise box using the [available official boxes](https://github.com/mitchellh/vagrant/wiki/Available-Vagrant-Boxes), for example: ```vagrant box add phpdevbox http://files.vagrantup.com/precise64.box``` (make sure it's named phpdevbox)
* Clone this repository
* Install submodules with ```git submodule update --init```
* After running ```vagrant up``` the box is set up using Puppet
* Webserver should be available under http://localhost:1337
* for special symfony2 settings please edit nginx conf files in files/nginx/

Installed components
--------------------

* [Nginx](http://nginx.org) using puppet module (https://github.com/example42/puppet-nginx)
* [php5.4-fpm](http://php-fpm.org)
* [composer](http://getcomposer.org)
* [git](http://git-scm.com/)
* [pear](http://pear.php.net/)
* [Node.js](http://nodejs.org/)
* [npm](http://npmjs.org/)
* [less](http://lesscss.org/)
* [MySQL](http://dev.mysql.com/downloads/mysql/)
* [MongoDB](http://www.mongodb.org/)
* [Capistrano](https://github.com/capistrano/capistrano)
* [capifony](http://capifony.org/)
* [sass](http://sass-lang.com/)
* [compass](http://compass-style.org/)
* Most of the [phpqatools](http://www.phpqatools.org) using puppet module (https://github.com/rafaelfelix/puppet-phpqatools)

Composer
---------
Composer is installed globally. Just run composer command in your cli.

$ composer self-update


Debugging
---------

If you want to debug your cli application using xdebug for example with Phpstorm just run this command before executing the cli app:

.. code-block:: sh

    $ export XDEBUG_CONFIG="idekey=phpstorm-xdebug remote_host=192.168.33.1 profiler_enable=1 default_enable=1 remote_enable=1 remote_handler=dbgp remote_port=9000 remote_autostart=0"

Hints
-----

**Startup speed**

To speed up the startup process use

.. code-block:: sh

    $ vagrant up --no-provision

after the first run. It just starts the virtual machine without provisioning of the recipes.

TODO
----
* switch between apache and nginx
* detailed vhost configuration with hostnames
* add more php extensions