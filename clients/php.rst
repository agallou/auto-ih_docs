Client API php
==============

Le client PHP se trouve sur `Github <https://github.com/agallou/auto-ih_php-api>`_

::

    include 'Genrsa.php';
    include 'Epmsi.php';

    $url = 'http://autoih.localhost/api.php';
    
    $genrsa = new Genrsa($url);
    $genrsa
      ->setPeriod('M0')
      ->setYear(2012)
      ->addFile('rss', 'rss.txt')
      ->addFile('autorisations', 'autorisations.txt')
      ->addFile('anohosp', 'anohosp.txt')
      ->launch()
      ->waitForStatus(array('SUCCESS', 'FAILURE'))
    ;

    file_put_contents('export_genrsa.zip', $genrsa->getFile('exported_zip'));


    $epmsi = new Epmsi($url);
    $epmsi
      ->setPeriod('M0')
      ->setYear(2012)
      ->addFile('export_genrsa', 'export_genrsa.zip')
      ->launch()
      ->waitForStatus(array('SUCCESS', 'FAILURE'))
    ;

    file_put_contents('export_epmsi.zip', $epmsi->getFile('exported_zip'));

