Installation
============

Installieren Sie das Modul :productname:`OXID eShop eVAT` für den OXID eShop ab Version 6.0.


|prerequisites|

* Sie haben den OXID eShop 7.0 oder höher installiert.
* Sie haben PHP 8.0 oder höher.


|procedure|


1. Öffnen Sie eine Shell und wechseln Sie ins Root-Verzeichnis des eShops (in dem die Datei :file:`composer.json` liegt).
   |br|
   Beispiel:

   .. code:: bash

      cd /var/www/oxideshop

#. Um die letzte veröffentlichte Version zu installieren, führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require oxid-esales/evat-module:^3.0

   Alternativ: Um die letzte unveröffentlichte Version von Github zu installieren, führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require oxid-esales/evat-module:dev-b-7.0.x

#. Bestätigen Sie die Abfragen.
#. Optional Löschen Sie alle Dateien und Ordner außer der Datei :file:`.htaccess` aus dem Verzeichnis :file:`/tmp` des Shops.

|result|


Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :productname:`OXID eShop eVAT` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module` (:ref:`oxdakc01`).

.. _oxdakc01:

.. figure:: /media/screenshots/oxdakc01.png
   :scale: 100 %
   :alt: Modul eVAT installiert

   Abb.: Modul eVAT installiert


Nächster Schritt: Um :productname:`OXID eShop eVAT` zu konfigurieren, wählen Sie :guilabel:`Weiter`.



.. Intern: oxdakc, Status: