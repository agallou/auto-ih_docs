/epmsi/mat2a/mco_stc/:annee/M0/send
===================================

Description
-----------

Envoie un fichier sur e-PMSI (MAT2A MCO).

Type
----

POST

Paramètres
----------


========= ===============================
Paramètre Libellé
========= ===============================
annee     Années supportées : 2011, 2012.
========= ===============================


Fichiers
--------

============= =============================
Argument      Libellé
============= =============================
export_genrsa Fichier ZIP exporté de GENRSA
============= =============================


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

==== =====================================
Code Libellé
==== =====================================
1    Fichier de exporté de GENRSA manquant
==== =====================================

Exemple
-------

Appel : ::

    curl -F export_genrsa=@export_genrsa.zip http://autoih.localhost/api.php/epmsi/mat2a/mco_stc/2012/M0/send

Retour : ::

    {"status":0,"message":"OK","content":{"id":"8c43201682751d9403a335b3dd0eb670"}}

