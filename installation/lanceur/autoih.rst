Configuration auto-ih
=====================

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
  genrsa_2012_path: 'C:\Program Files\POP-T2A\GENRSA_2012\WGENRSA.exe'
  genrsa_2011_path: 'C:\Program Files\POP-T2A\GENRSA_2011\WGENRSA.exe'
  finess: "000000000"


.. _genrsa_working_dir:

genrsa_working_dir
------------------

Chemin vers le dossier ou déposer les fichiers envoyés à l'API GENRSA. Doit être accessible en ecriture par apache.

.. _epmsi_working_dir:

epmsi_working_dir
-----------------

Chemin vers le dossier ou déposer les fichiers envoyés à l'API e-PMSI. Doit être accessible en ecriture par apache.

sahi_userdata
-------------

Chemin vers le dossier ou sahi conserve les fichiers téléchargés. Généralement %HOMEPATH\sahi\userdata.

sahi_host
---------

Si sahi à été installé localement conserver cette valeur à localhost.

epmsi_user
----------

Identifiant à utiliser pour accéder à `<https://www.epmsi.atih.sante.fr/>`_.

epmsi_password
--------------

Mot de passe à utiliser pour accéder à `<https://www.epmsi.atih.sante.fr/>`_.

worker_epmsi_dir
----------------

Utilisé par la machine sous windows. Chemin vers lequel accéder aux fichiers déposés par :ref:`epmsi_working_dir`. Doit être accessible en écriture.

worker_genrsa_dir
-----------------

Utilisé par la machine sous windows. Chemin vers lequel accéder aux fichiers déposés par :ref:`genrsa_working_dir`. Doit être accessible en écriture.

genrsa_2012_path
----------------

A chaque année est associée une version de GENRSA (généralement la dernière disponible pour l'année concernée). Pour cette raison il est préférable de ne pas installer GENRSA dans le dossier par défaut mais de créer un dossier par année pour ainsi avoir plusieurs versions de GENRSA sur la machine. Pour executer GENRSA, auto-ih à besoin de connaitre le chemin vers l'executable. genrsa_2012_path permet d'indiquer le chemin vers l'executable WGENRSA.exe de l'année concernée.

genrsa_2011_path
----------------

A chaque année est associée une version de GENRSA (généralement la dernière disponible pour l'année concernée). Pour cette raison il est préférable de ne pas installer GENRSA dans le dossier par défaut mais de créer un dossier par année pour ainsi avoir plusieurs versions de GENRSA sur la machine. Pour executer GENRSA, auto-ih à besoin de connaitre le chemin vers l'executable. genrsa_2011_path permet d'indiquer le chemin vers l'executable WGENRSA.exe de l'année concernée.

finess
------

Immatriculation de 9 chiffres représentant l'établissement dont les données seront importées. Doit être le même numéro que celui présent dans les fichiers de RUM importés.

