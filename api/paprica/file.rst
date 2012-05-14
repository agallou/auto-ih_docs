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

================ =================================================================
Valeur           Description
================ =================================================================
exported_zip     Fichier ZIP exporté de PAPRICA.
log              Compte-rendu de PAPRICA
dif              Différence de groupage
chainage_log     Compte-rendu de chaînage
chainage_err     Erreurs de chaînage
err_non_bloq     Visualisation des erreurs non bloquantes de groupage
err_bloq         Visualisation des erreurs bloquantes de groupage
leg              Synthèse des erreurs de groupage et des contrôles complémentaires
ehpa_jours_suppr EHPA - Journées supprimées car hors convention
temps            Temps pris par les différents traitements de PAPRICA
================ =================================================================


