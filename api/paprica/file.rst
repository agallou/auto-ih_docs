/paprica/:annee/M0/:id/file/:type
=================================


Description
-----------

Renvoi le fichier ZIP d'export, ainsi que les différents fichiers journaux de PAPRICA.

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
type      type de fichier à récupérer
========= ============================================


Valeurs pour le paramètre type
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

============ =================================================================
Valeur       Description
============ =================================================================
exported_zip Fichier ZIP exporté de PAPRICA.
leg          Synthèse des erreurs de groupage et des contrôles complémentaires
============ =================================================================


