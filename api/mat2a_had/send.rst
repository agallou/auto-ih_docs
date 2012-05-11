/epmsi/mat2a/had/:annee/M0/send
===============================

Description
-----------

Envoie un fichier sur e-PMSI (MAT2A HAD).

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

============== ==============================
Argument       Libellé
============== ==============================
export_paprica Fichier ZIP exporté de PAPRICA
============== ==============================


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

==== ======================================
Code Libellé
==== ======================================
1    Fichier de exporté de PAPRICA manquant
==== ======================================

Exemple
-------

Appel : ::

    curl -F export_paprica=@export_paprica.zip http://autoih.localhost/api.php/epmsi/mat2a/had/2012/M0/send

Retour : ::

    {"status":0,"message":"OK","content":{"id":"8c43201682751d9403a335b3dd0eb670"}}

