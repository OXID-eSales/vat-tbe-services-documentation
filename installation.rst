Installation
============

Installieren Sie das Modul :productname:`OXID eShop eVAT` für den OXID eShop Version 7.


|prerequisites|

* Sie haben OXID eShop 7.0.x.

.. todo: #HR: "PHP 8.0 oder höher."? -- ist  das relevant, wenn ich den shop habe, wenn 7.1 8.1/8.2 hat?

|procedure|


1. Öffnen Sie eine Shell und wechseln Sie ins Root-Verzeichnis des eShops (in dem die Datei :file:`composer.json` liegt).
   |br|
   Beispiel:

   .. code:: bash

      cd /var/www/oxideshop

#. Um die letzte veröffentlichte Version zu installieren, führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require oxid-esales/evat-module:^3.0.0

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