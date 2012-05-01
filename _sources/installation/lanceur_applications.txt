Lanceur d'applications
======================

Il faut installer : 

* `genrsa <http://download.atih.sante.fr/index.php?lettre=G>`_
*  `.net framework 3.5 <http://www.microsoft.com/downloads/fr-fr/details.aspx?familyid=333325fd-ae52-4e35-b531-508d977d32a6>`_
* `sahi <http://sahi.co.in/w/>`_
* `php <http://windows.php.net/download/>`_


Configurer sahi
---------------

dans le fichier::

    %appdata%/sahi/userdata/config/userdata.properties 

ajouter::

    keytool.path=C:\Program Files\Java\jre6\bin\keytool.exe

pour permettre d'accéder aux sites en https.

Démarrer ensuite le navigateur via sahi et accéder une fois à epmsi pour autoriser les certificats.


Lancement
---------

Lancer le worker::

    SET PHP_PATH="C:\Program Files\PHP\php.exe" && .\data\run.bat

