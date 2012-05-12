Client API PHP
==============

Le client PHP se trouve sur `Github <https://github.com/agallou/auto-ih_php-api>`_

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
