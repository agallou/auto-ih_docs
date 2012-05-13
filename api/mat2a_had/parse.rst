/epmsi/mat2a/had/:annee/M0/parse
================================

Description
-----------

Prend en paramètre le fichier ZIP contenant les exports HTML de MAT2A et renvoie un tabeau contenant certaines des valeurs de ces tableaux.

Type
----

POST

Fichiers
--------

============ ===========================================
Argument 
============ ===========================================
export_epmsi Fichier ZIP exporté de e-PMSI.
============ ===========================================


Retour
------

01b_tot2
^^^^^^^^

Tableau 1B Valorisation - Valorisation

================ =======================================
Clef
================ =======================================
coeff_geo        Coefficient géographique
nb_jours_valo    Nb journées valorisées
valo_brute       Valorisation brute
valo_corrigee    Valorisation corrigée
valo_ehpa        Dont valorisation en EHPA
valo_am          Valorisation AM
================ =======================================

01d_synthano
^^^^^^^^^^^^

Tableau 1D - Synthèse de la procédure de chainage des résumés PMSI

========================= ==============================================================
Clef
========================= ==============================================================
nb_total_sejours          Nombre total de séjours
sej_sans_clef             Séjours sans clé de chainage ou générée sans no. assuré social
nb_readmissions           Nombre de réadmissions
nb_readmissions_2j        Nombre de réadmissions dans un délai <2j
delai_median_readmissions Délai médian des réadmissions, en jours
========================= ==============================================================


Exemple
-------

Appel : ::

  curl -F export_epmsi=@/export_epmsi.zip http://autoih.localhost/api.php/epmsi/mat2a/had/2012/M0/parse

Retour : ::

  {
    "status":0,
    "message":"OK",
    "content":{
      "01b_tot2":{
        "coeff_geo":"1.00",
        "nb_jours_valo":"1000.00",
        "valo_brute":"70000.30",
        "valo_corrigee":"70000.30",
        "valo_ehpa":null,
        "valo_am":"65000.00"
      },
      "01d_synthano":{
        "nb_total_sejours":"50",
        "sej_sans_clef":"10",
        "nb_readmissions":"5",
        "nb_readmissions_2j":"0",
        "delai_median_readmissions":"16"
      }
    }
  }

