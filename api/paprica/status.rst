/paprica/:annee/M0/:id/status
=============================

Description
-----------

Statut du passage des fichiers dans GENRSA.

Type
----

GET

Paramètres
----------

========= ============================================
Paramètre 
========= ============================================
annee     Année supportée : 2012.
id        id renvoyé par l'api :doc:`send`
========= ============================================


Retour
------

Succès
^^^^^^

+---------+-----------+
|Paramètre|Libellé    |
+=========+===========+
|status   | * SUCCESS |
|         | * WAITING |
|         | * RUNNING |
|         | * ERROR   |
+---------+-----------+

Exemple
-------

Appel : ::

  curl  http://autoih.localhost/api.php/paprica/2012/M0/69a7d9f2c4560159d39731b3c91515a5/status

Retour : ::

  {"status":0,"message":"OK","content":{"status":"RUNNING"}}

