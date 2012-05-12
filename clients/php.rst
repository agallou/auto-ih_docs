Client API PHP
==============

Le client PHP se trouve sur Github (`<https://github.com/agallou/auto-ih_php-api>`_).

Voici un exemple qui va passer un fichier de RUM, d'autorisation et anohosp dans GENRSA 2012 (sur la période M0), va récupérer le fichier ZIP exporté de GENRSA en le plaçant dans export_genrsa.zip. Puis va envoyer ce fichier sur MAT2A et récupérer l'export des tableaux de MAT2A dans un fichier zip en la plaçant dans export_epmsi.zip.

.. code-block:: php

  <?php
    require_once 'Autoload.php';
    AutoihAutoload::register();
    
    $connection = new AutoihConnection('http://autoih.localhost/api.php');
    
    $genrsa = new Genrsa($connection);
    $genrsa
      ->setPeriod('M0')
      ->setYear(2012)
      ->addFile('rss', 'rss.txt')
      ->addFile('autorisations', 'autorisations.txt')
      ->addFile('anohosp', 'anohosp.txt')
      ->launch()
      ->waitEnd()
      ->writeFile('exported_zip', 'export_genrsa.zip')
    ;
    
    $mat2a = new Mat2a($connection);
    $mat2a
      ->setType('mco_stc')
      ->setPeriod('M0')
      ->setYear('2012')
      ->addFile('export_genrsa', 'export_genrsa.zip')
      ->launch()
      ->waitEnd()
      ->writeFile('exported_zip', 'export_epmsi.zip')
    ;

Il existe a un raccourci sur l'objet Genrsa pour créer un objet Mat2a avec les attributs années période et date déjà renseignés : la méthode createMat2. Le code ci-dessus peut aussi s'écrire de cette façon : 

.. code-block:: php

  <?php
    require_once 'Autoload.php';
    AutoihAutoload::register();
    
    $genrsa = new Genrsa(new AutoihConnection('http://autoih.localhost/api.php'));

    $genrsa
      ->setPeriod('M0')
      ->setYear(2012)
      ->addFile('rss', 'rss.txt')
      ->addFile('autorisations', 'autorisations.txt')
      ->addFile('anohosp', 'anohosp.txt')
      ->launch()
      ->waitEnd()
      ->writeFile('exported_zip', 'export_genrsa.zip')
    ;
    
    $mat2a = $genrsa->createMat2a();
    $mat2a
      ->addFile('export_genrsa', 'export_genrsa.zip')
      ->launch()
      ->waitEnd()
      ->writeFile('exported_zip', 'export_epmsi.zip')
    ;
