Principes
---------

auto-ih nécéssite 2 composants pour fonctionner : 

* un :doc:`serveur_web` : 

 * écoute les requêtes effectuées via l'API, 
 * place les fichiers en demande de traitement dans un dossier. 
 * permet de récupérer les exports effecutés par le lanceur d'application.

* un :doc:`lanceur_applications` : (doit nécéssairement être lancé sous windows). 

 * traite les fichiers se trouvant dans un dossier, 
 * effectue les imports dans GENRSA puis e-PMSI
 * stocke les exports respectifs dans le même dossier que celui se trouvant les fichiers importés.

