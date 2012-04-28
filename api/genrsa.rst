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


Exemple utilisant CURL
""""""""""""""""""""""

Appel : ::

    curl -F rss=@rum.txt -F autorisations=@autorisations.txt -F anohosp=@anohosp.txt http://autoih.localhost/api.php/genrsa/2012/send

Retour : ::

    {"status":0,"message":"OK","content":{"id":"8c43201682751d9403a335b3dd0eb670"}}


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

Exemple utilisant CURL
""""""""""""""""""""""

Appel : ::

  curl  http://autoih.localhost/api.php/genrsa/2012/69a7d9f2c4560159d39731b3c91515a5/status

Retour : ::

  {"status":0,"message":"OK","content":{"status":"RUNNING"}}


/genrsa/2012/:id/file/:type
---------------------------


Description
^^^^^^^^^^^

Renvoi le fichier ZIP en sortie de GENRSA.

Type
^^^^

GET
