/paprica/:annee/M0/send
=======================

Description
-----------

Envoie des fichiers pour passage dans PAPRICA.

Type
----

POST

Paramètres
----------

========= =============================
Paramètre Libellé
========= =============================
annee     Année supportée : 2012.
========= =============================


Fichiers
--------

============= =======================
Argument      Libellé
============= =======================
rpss          Fichier de RPSS
ehpa          Fichier de conventions EHPA
anohosp       Fichier ANOHOSP
============= =======================


Retour
------

Succès
^^^^^^

========= =======
Paramètre Libellé
========= =======
id        id du traitement, à réutiliser lors des autres appels à l'API.
========= =======

Erreur
^^^^^^

==== ===============================
Code Libellé
==== ===============================
1    Fichier de RPSS manquant
2    Fichier de conventions EHPA manquant
3    Fichier ANOHOSP manquant
==== ===============================


Exemple
-------

Appel : ::

    curl -F rpss=@rpss.txt -F ehpa=@ehpa.txt -F anohosp=@anohosp.txt http://autoih.localhost/api.php/paprica/2012/M0/send

Retour : ::

    {"status":0,"message":"OK","content":{"id":"8c43201682751d9403a335b3dd0eb670"}}

