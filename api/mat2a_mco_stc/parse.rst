/epmsi/mat2a/mco_stc/:annee/M0/parse
====================================

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

34_a
^^^^

Tableau 34 A Valorisation - Tableau de Synthèse

============================== ==========================================================
Clef
============================== ==========================================================
nb_sej-transmisa               Nb Séjours/Séances - Séjours transmis
montant_br-sej_transmis        Montant BR - Séjours transmis
nb_sej-non_fact_am_hors_po     Nb Séjours/Séances - Séjours non facturable à l'AM hors PO
montant_br-non_fact_am_hors_po Montant BR - Séjours non facturable à l'AM hors PO
============================== ==========================================================


34_c
^^^^

Tableau 34 C Valorisation - Récapitulation activité - Valorisation

================================= =====================================================================================
Clef
================================= =====================================================================================
br_tot-coeff_geo                  Montant BR total - Coefficient géographique
br_tot-coeff_trans                Montant BR total - Coefficient de transition
br_tot-valo_ghs                   Montant BR total - Valorisation des GHS  
br_tot-valo_exb                   Montant BR total - Valorisation extrême bas (à déduire)
br_tot-valo_sej_rehosp_meme_ghm   Montant BR total - Valorisation séjours avec rehosp dans même GHM (à déduire)
br_tot-valo_exh                   Montant BR total - Valorisation journées extrême haut
br_tot-valo_actes_ghs_9615_hospit Montant BR total - Valorisation actes GHS 9615 en Hospit.
br_tot-valo_suppl_radoth_pedia    Montant BR total - Valorisation suppléments radiothérapie pédiatrique
br_tot-valo_suppl_antepartum      Montant BR total - Valorisation suppléments antepartum   
br_tot-valo_actes_rdth_hospit     Montant BR total - Valorisation actes RDTH en Hospit.
br_tot-valo_suppl_rea             Montant BR total - Valorisation suppléments de réanimation
br_tot-valo_suppl_rea_pedia       Montant BR total - Valorisation suppléments de réa pédiatrique
br_tot-valo_suppl_neo_sans_si     Montant BR total - Valorisation suppléments de néonat sans SI
br_tot-valo_suppl_neo_avec_si     Montant BR total - Valorisation suppléments de néonat avec SI
br_tot-valo_suppl_rea_neo         Montant BR total - Valorisation suppléments de réanimation néonat
br_tot-valo_po                    Montant BR total - Valorisation prélévements d'organe
br_tot-valo_actes_caiss_hype_sus  Montant BR total - Valorisation des actes de caissons hyperbares en sus
br_tot-valo_suppl_dial            Montant BR total - Valorisation suppléments de dialyse
br_tot-valo_sc_valides            Montant BR total - Valorisation suppléments de surveillance continue validés
br_tot-valo_si_valides            Montant BR total - Valorisation suppléments de soins intensifs validés
br_tot-total_valo                 Montant BR total - Total valorisation
am-coeff_geo                      Montant remboursé AM - Coefficient géographique
am-coeff_trans                    Montant remboursé AM - Coefficient de transition
am-valo_ghs                       Montant remboursé AM - Valorisation des GHS  
am-valo_exb                       Montant remboursé AM - Valorisation extrême bas (à déduire)
am-valo_sej_rehosp_meme_ghm       Montant remboursé AM - Valorisation séjours avec rehosp dans même GHM (à déduire)
am-valo_exh                       Montant remboursé AM - Valorisation journées extrême haut
am-valo_actes_ghs_9615_hospit     Montant remboursé AM - Valorisation actes GHS 9615 en Hospit.
am-valo_suppl_radoth_pedia        Montant remboursé AM - Valorisation suppléments radiothérapie pédiatrique
am-valo_suppl_antepartum          Montant remboursé AM - Valorisation suppléments antepartum   
am-valo_actes_rdth_hospit         Montant remboursé AM - Valorisation actes RDTH en Hospit.
am-valo_suppl_rea                 Montant remboursé AM - Valorisation suppléments de réanimation
am-valo_suppl_rea_pedia           Montant remboursé AM - Valorisation suppléments de réa pédiatrique
am-valo_suppl_neo_sans_si         Montant remboursé AM - Valorisation suppléments de néonat sans SI
am-valo_suppl_neo_avec_si         Montant remboursé AM - Valorisation suppléments de néonat avec SI
am-valo_suppl_rea_neo             Montant remboursé AM - Valorisation suppléments de réanimation néonat
am-valo_po                        Montant remboursé AM - Valorisation prélévements d'organe
am-valo_actes_caiss_hype_sus      Montant remboursé AM - Valorisation des actes de caissons hyperbares en sus
am-valo_suppl_dial                Montant remboursé AM - Valorisation suppléments de dialyse
am-valo_sc_valides                Montant remboursé AM - Valorisation suppléments de surveillance continue validés
am-valo_si_valides                Montant remboursé AM - Valorisation suppléments de soins intensifs validés
am-total_valo                     Montant remboursé AM - Total valorisation
================================= =====================================================================================

Exemple
-------

Appel : ::

  curl -F export_epmsi=@/export_epmsi.zip http://autoih.localhost/api.php/epmsi/mat2a/mco_stc/2012/M0/parse

Retour : ::

    {
      "status": 0,
      "message": "OK",
      "content": {
        "34_a": {
          "nb_sej-transmis": "1",
          "montant_br-sej_transmis": "1057.66",
          "nb_sej-non_fact_am_hors_po": "1",
          "montant_br-non_fact_am_hors_po": "1057.66"
        },
        "34_c": {
          "br_tot-coeff_geo": null,
          "br_tot-coeff_trans": null,
          "br_tot-valo_ghs": "0.00",
          "br_tot-valo_exb": "0.00",
          "br_tot-valo_sej_rehosp_meme_ghm": "0.00",
          "br_tot-valo_exh": "0.00",
          "br_tot-valo_actes_ghs_9615_hospit": "0.00",
          "br_tot-valo_suppl_radoth_pedia": "0.00",
          "br_tot-valo_suppl_antepartum": "0.00",
          "br_tot-valo_actes_rdth_hospit": "0.00",
          "br_tot-valo_suppl_rea": "0.00",
          "br_tot-valo_suppl_rea_pedia": "0.00",
          "br_tot-valo_suppl_neo_sans_si": "0.00",
          "br_tot-valo_suppl_neo_avec_si": "0.00",
          "br_tot-valo_suppl_rea_neo": "0.00",
          "br_tot-valo_po": "0.00",
          "br_tot-valo_actes_caiss_hype_sus": "0.00",
          "br_tot-valo_suppl_dial": "0.00",
          "br_tot-valo_sc_valides": "0.00",
          "br_tot-valo_si_valides": "0.00",
          "br_tot-total_valo": "0.00",
          "am-coeff_geo": null,
          "am-coeff_trans": null,
          "am-valo_ghs": null,
          "am-valo_exb": null,
          "am-valo_sej_rehosp_meme_ghm": null,
          "am-valo_exh": null,
          "am-valo_actes_ghs_9615_hospit": null,
          "am-valo_suppl_radoth_pedia": null,
          "am-valo_suppl_antepartum": null,
          "am-valo_actes_rdth_hospit": null,
          "am-valo_suppl_rea": null,
          "am-valo_suppl_rea_pedia": null,
          "am-valo_suppl_neo_sans_si": null,
          "am-valo_suppl_neo_avec_si": null,
          "am-valo_suppl_rea_neo": null,
          "am-valo_po": "0.00",
          "am-valo_actes_caiss_hype_sus": null,
          "am-valo_suppl_dial": null,
          "am-valo_sc_valides": null,
          "am-valo_si_valides": null,
          "am-total_valo": "0.00"
        }
      }
    }


