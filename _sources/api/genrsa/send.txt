/genrsa/:annee/send
===================

Description
-----------

Envoi des fichiers pour passage dans GENRSA.

Type
----

POST

Paramètres
----------

========= =============================
Paramètre Libellé
========= =============================
annee     Années supportées 2011, 2012.
========= =============================


Fichiers
--------

============= =======================
Argument      Libellé
============= =======================
rss           Fichier de RUM
autorisations Fichier d'autorisations
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
1    Fichier de RUM manquant
2    Fichier d'autorsations manquant
3    Fichier ANOHOSP manquant
==== ===============================


Exemple
-------

Appel : ::

    curl -F rss=@rum.txt -F autorisations=@autorisations.txt -F anohosp=@anohosp.txt http://autoih.localhost/api.php/genrsa/2012/send

Retour : ::

    {"status":0,"message":"OK","content":{"id":"8c43201682751d9403a335b3dd0eb670"}}

