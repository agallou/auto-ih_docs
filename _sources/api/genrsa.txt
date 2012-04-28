Genrsa
======

/genrsa/2012/send
-----------------

Description
^^^^^^^^^^^

Envoi des fichiers pour passage dans GENRSA.

Type
^^^^

POST

Fichiers
^^^^^^^^^

============= =======================
Argument      Libellé
============= =======================
rss           Fichier de RUM
autorisations Fichier d'autorisations
anohosp       Fichier ANOHOSP
============= =======================


Retour
^^^^^^

Succès
"""""""

========= =======
Paramètre Libellé
========= =======
id        id du traitement, à réutiliser lors des autres appels à l'API.
========= =======

Erreur
""""""

==== ===============================
Code Libellé
==== ===============================
1    Fichier de RUM manquant
2    Fichier d'autorsations manquant
3    Fichier ANOHOSP manquant
==== ===============================


/genrsa/2012/:id/status
-----------------------

Description
^^^^^^^^^^^

Statut du passage des fichiers dans GENRSA.

Type
^^^^

GET

Paramètres
^^^^^^^^^^

========= ==========================================
Paramètre 
========= ==========================================
id        id renvoyé par l'api /genrsa/2012/:id/send
========= ==========================================


Retour
^^^^^^

Succès
"""""""

+---------+-----------+
|Paramètre|Libellé    |
+=========+===========+
|status   | * SUCCESS |
|         | * WAITING |
|         | * RUNNING |
|         | * ERROR   |
+---------+-----------+          


/genrsa/2012/:id/file/:type
---------------------------


Description
^^^^^^^^^^^

Renvoi le fichier ZIP en sortie de GENRSA.

Type
^^^^

GET

Epmsi
=====

/epmsi/2012/send
----------------

/epmsi/2012/:id/status
----------------------

/epmsi/2012/:id/file/:type
--------------------------
