Lanceur d'applications
======================

Installation dépendances
------------------------

Il faut installer : 

* `genrsa <http://download.atih.sante.fr/index.php?lettre=G>`_
*  `.net framework 3.5 <http://www.microsoft.com/downloads/fr-fr/details.aspx?familyid=333325fd-ae52-4e35-b531-508d977d32a6>`_
* `sahi <http://sahi.co.in/w/>`_
* `php <http://windows.php.net/download/>`_


Configuration sahi
------------------

dans le fichier::

    %appdata%/sahi/userdata/config/userdata.properties 

ajouter::

    keytool.path=C:\Program Files\Java\jre6\bin\keytool.exe

pour permettre d'accéder aux sites en https.

Démarrer ensuite le navigateur via sahi et accéder une fois à epmsi pour autoriser les certificats.


Configuration auto-ih
---------------------

auto-ih se configure via un fichier YAML, celui-ci doit être placé dans config/configuration.yml.

Ci-dessous un exemple de configuration.

.. code-block:: yaml

  genrsa_working_dir: "/media/autoih_worker/genrsa/"
  epmsi_working_dir: "/media/autoih_worker/epmsi/"
  sahi_userdata: "C:\Documents and Settings\Administrateur\sahi\userdata"
  sahi_host: "localhost"
  epmsi_user: "userid"
  epmsi_password: "password"
  worker_epmsi_dir: 'X:\epmsi'
  worker_genrsa_dir: 'X:\genrsa'
  genrsa_2012_path: 'C:\Program Files\POP-T2A\GENRSA\WGENRSA.exe'
  genrsa_2011_path: 'C:\Program Files\POP-T2A\GENRSA_2011\WGENRSA.exe'
  finess: "000000000"

Lancement
---------

Lancer le worker::

    SET PHP_PATH="C:\Program Files\PHP\php.exe" && .\data\run.bat

