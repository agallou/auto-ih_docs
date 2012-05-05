e-PMSI
======

/epmsi/:annee/send
------------------

Description
^^^^^^^^^^^

Envoie un fichier sur e-PMSI

Type
^^^^

POST

Paramètres
^^^^^^^^^^


========= =============================
Paramètre Libellé
========= =============================
annee     Années supportées 2011, 2012.
========= =============================


Fichiers
^^^^^^^^

============= =============================
Argument      Libellé
============= =============================
export_genrsa Fichier ZIP exporté de GENRSA
============= =============================


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

==== =====================================
Code Libellé
==== =====================================
1    Fichier de exporté de GENRSA manquant
==== =====================================

Exemple
^^^^^^^

Appel : ::

    curl -F export_genrsa=@export_genrsa.zip http://autoih.localhost/api.php/epmsi/2012/send

Retour : ::

    {"status":0,"message":"OK","content":{"id":"8c43201682751d9403a335b3dd0eb670"}}


/epmsi/:annee/:id/status
------------------------

Description
^^^^^^^^^^^

Statut du passage des fichiers sur e-PMSI.

Type
^^^^

GET

Paramètres
^^^^^^^^^^

========= ===========================================
Paramètre 
========= ===========================================
annee     Années supportées 2011, 2012.
id        id renvoyé par l'api /epmsi/:annee/:id/send
========= ===========================================


Retour
^^^^^^

Succès
""""""

+---------+-----------+
|Paramètre|Libellé    |
+=========+===========+
|status   | * SUCCESS |
|         | * WAITING |
|         | * RUNNING |
|         | * ERROR   |
+---------+-----------+


Exemple
^^^^^^^

Appel : ::

  curl  http://autoih.localhost/api.php/epmsi/2012/69a7d9f2c4560159d39731b3c91515a5/status

Retour : ::

  {"status":0,"message":"OK","content":{"status":"RUNNING"}}


/epmsi/:annee/:id/file/:type
---------------------------


Description
^^^^^^^^^^^

Renvoi le fichier ZIP contenant les exports HTML de e-PMSI.

Type
^^^^

GET

Paramètres
^^^^^^^^^^

========= ===========================================
Paramètre 
========= ===========================================
annee     Années supportées 2011, 2012.
id        id renvoyé par l'api /epmsi/:annee/:id/send
type      exported_zip
========= ===========================================


