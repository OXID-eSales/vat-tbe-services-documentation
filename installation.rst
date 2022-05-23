Installation
============

Installieren Sie das Modul :productname:`eVAT` für den OXID eShop ab Version 6.0.


|prerequisites|

* Sie haben den OXID eShop 6.0 oder höher installiert.
* Sie haben PHP 5.6 oder höher.


|procedure|


1. Öffnen Sie eine Shell und wechseln Sie ins Root-Verzeichnis des eShops (in dem die Datei :file:`composer.json` liegt).
   |br|
   Beispiel:

   .. code:: bash

      cd /var/www/oxideshop

#. Um die letzte veröffentlichte Version zu installieren, führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require oxid-esales/evat-module:^2.0

   Alternativ: Um die letzte unveröffentlichte Version von Github zu installieren, führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require oxid-esales/evat-module:dev-master

#. Bestätigen Sie die Abfragen.
#. Löschen Sie alle Dateien und Ordner außer der Datei :file:`.htaccess` aus dem Verzeichnis :file:`/tmp` des Shops.

|result|

.. todo: Verifizieren:

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :productname:`eVAT` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module`.


.. todo: #tbd Bild ergänzen


Nächster Schritt: Um :productname:`eVAT` zu konfigurieren, wählen Sie :guilabel:`Weiter`.



.. Intern: oxdakc, Status: