Serveur Web
===========

Prérequis :

* php
* git


Récupérer composer::

    curl -s http://getcomposer.org/installer | php

Puis installer les dépendances::

    php composer.phar install


Exemple utilisation virtualhost::

    NameVirtualHost *
    <VirtualHost *>
    
        ServerName autoih.localhost
        ServerAdmin webmaster@localhost
    
        DocumentRoot /pathtoautoih/www
        DirectoryIndex index.php
        <Directory "/pathtoautoih/www">
            AllowOverride All
            Allow from All
        </Directory>
    </VirtualHost>
  
