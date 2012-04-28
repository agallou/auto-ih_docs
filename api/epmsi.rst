e-PMSI
======

/epmsi/2012/send
-----------------

Description
^^^^^^^^^^^

Envoi un fichier sur e-PMSI

Type
^^^^

POST

Fichiers
^^^^^^^^^

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


/epmsi/2012/:id/status
-----------------------

Description
^^^^^^^^^^^

Statut du passage des fichiers sur e-PMSI.

Type
^^^^

GET

Paramètres
^^^^^^^^^^

========= ==========================================
Paramètre 
========= ==========================================
id        id renvoyé par l'api /epmsi/2012/:id/send
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


/epmsi/2012/:id/file/:type
---------------------------


Description
^^^^^^^^^^^

Renvoi le fichier ZIP contenant les exports HTML de e-PMSI.

Type
^^^^

GET
