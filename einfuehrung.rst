Wofür/Wofür nicht?
==================

Integrieren Sie mit dem Modul :productname:`OXID eShop eVAT` die Besteuerung von Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen in Ihren OXID eShop.

.. todo: #ProdMan:klären: Wenn el. Artikel, dann Modul nötig; hilft auch bei anderen Produkten, aber da nicht nötig; wenn business > 100000 Euro auch mit 19% nach Österreich; Jahresumsatz
   Große eShops: aus Österreich bestellt, dann 19 -> Modul würde helfen: wenn gezwungen, MWSt korrekt auszuweisen, dann Modul: Steuerberater fragen

Gesetzliche Grundlage
---------------------

Das Modul :productname:`OXID eShop eVAT` hilft Ihnen, die EU-Durchführungsverordnung Nr. 1042/2013 bezüglich des Orts der Dienstleistung einzuhalten.

Diese EU-Durchführungsverordnung besagt, dass Händler und Dienstleister ab dem 1. Januar 2015 beim Verkauf ihrer elektronisch erbrachten Dienstleistungen die Mehrwertsteuer des EU-Landes abführen müssen, aus dem der Privatkunde ("Verbraucher (Nichtsteuerpflichtiger)") kommt. Vorher war es die Mehrwertsteuer des Landes, in dem das eigene Unternehmen ansässig ist.

Weitere Informationen finden Sie auf den Seiten der Europäischen Kommission unter: `ec.europa.eu/taxation_customs/news/vat-updated-version-moss-report-has-just-been-published-2016-05-12_de <https://ec.europa.eu/taxation_customs/news/vat-updated-version-moss-report-has-just-been-published-2016-05-12_de>`_.

Technische Umsetzung
--------------------

Artikel, die Sie in Ihrem OXID eShop als elektronisch erbrachte Dienstleistungen definieren, sind beim Kauf als solche gekennzeichnet.

:productname:`OXID eShop eVAT` ermittelt das Herkunftsland des Privatkunden (B2C) nach der Rechnungsadresse und berechnet entsprechend die jeweilige Mehrwertsteuer.

* Ein OXID eShop :emphasis:`ohne` das Modul :productname:`OXID eShop eVAT` verwendet auch bei Privatkunden aus EU-Ländern immer den Mehrwertsteuersatz, den Sie im Administrationsbereich unter :menuselection:`Stammdaten --> Grundeinstellungen --> Einstell. --> Mehrwertsteuer` als Standard festgelegt haben.
* Ein OXID eShop :emphasis:`mit` dem Modul :productname:`OXID eShop eVAT` berechnet die Mehrwertsteuer für Artikel, die Sie in Ihrem OXID eShop als elektronische Produkte oder Dienstleistungen definiert haben, mit dem Mehrwertsteuersatz, der dem ermittelten Standort des Privatkunden entspricht.
  |br|
  Für alle übrigen Artikel wird der Mehrwertsteuersatz herangezogen, der als Standard im Shop gilt.

Alle der Berechnung zugrunde liegenden Daten werden bei der Bestellung gespeichert.

Ihre Vorteile
-------------

* Definieren Sie Artikel einzeln oder kategorieweise als elektronische Produkte oder Dienstleistungen und ordnen Sie die Mehrwertsteuersätze für die gewünschten Länder zu.
* Nutzen Sie dabei

  * die Protokollierung des Kundenstandortes bei Bestellungen von elektronischen Produkten oder Dienstleistungen
  * die Speicherung der USt-ID-Nummer mit Datum und Uhrzeit als Nachweis für steuerpflichtige Kunden ("Unternehmen (Steuerpflichtige)").
    |br|
    Bei steuerpflichtigen Kunden wird in der Rechnung der Nettopreis ohne Mehrwertsteuer ausgewiesen.
* Erweitern Sie :productname:`OXID eShop eVAT` bei Bedarf um eigene Bestimmungsmethoden.

Funktionsweise
--------------


Informationen zur Mehrwertsteuer aus Kundensicht
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Im Frontend werden alle Artikel, mit denen Sie elektronisch erbrachte Dienstleistungen anbieten, mit zwei Sternchen ** markiert (:ref:`oxdaka01`, Pos. 1).

Diese Markierung am Artikelpreis erscheint auf der Startseite, in der Kategorie-Ansicht, der Detailseite des Artikels und an verschiedenen anderen Stellen.

.. _oxdaka01:

.. figure:: /media/screenshots/oxdaka01.png
   :class: with-shadow
   :width: 650
   :alt: Auszeichnung elektronisch erbrachter Dienstleistungen: Beispiel Artikel-Detailansicht

   Abb.: Auszeichnung elektronisch erbrachter Dienstleistungen


Am unteren rechten Ende einer jeden Seite des Frontends weisen die zwei Sternchen :guilabel:`**` auf eine elektronisch erbrachte Dienstleistung hin (:ref:`oxdaka01`, Pos. 2).

Ein Link (:ref:`oxdaka01`, Pos. 2) ruft die Seite auf, auf der Sie als Shopbetreiber Ihre Kunden detailliert über Zahlung und Lieferung Ihrer Ware informieren.
|br|
Den Inhalt dieser Seite bearbeiten Sie im Administrationsbereich unter :menuselection:`Kundeninformationen --> CMS-Seiten` (siehe :ref:`konfiguration:Kundeninformationen zu Mehrwertsteuersätzen ergänzen`).


Der Bestellprozess aus Kundensicht
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Legt Ihr Kunde einen Artikel, mit Sie elektronisch erbrachte Dienstleistungen anbieten, in den Warenkorb, dann werden die zwei Sternchen :guilabel:`**` bei der Mehrwertsteuer angezeigt (:ref:`oxdaka02`, Pos. 1).

Eine Meldung weist Ihren Kunden darauf hin, auf welchem Land die angezeigte Mehrwertsteuer basiert und dass sich die Mehrwertsteuer ändern kann, sobald der Kunde im Shop angemeldet ist (:ref:`oxdaka02`, Pos. 2).

.. _oxdaka02:

.. figure:: /media/screenshots/oxdaka02.png
   :class: with-shadow
   :width: 650
   :alt: Bestellschritt 1 mit Hinweis auf MwSt.-Berechnung

   Abb.: Bestellschritt 1 mit Hinweis auf MwSt.-Berechnung


Die Mehrwertsteuer wird nach Anmeldung oder nach Angeben der Rechnungsadresse berechnet, nachdem :productname:`OXID eShop eVAT` den Kundenstandort ermittelt hat (siehe :ref:`konfiguration:Bestimmen des Kundenstandorts konfigurieren`).

Eine Meldung weist den Kunden erneut darauf hin, welches Land Grundlage für die Berechnung der Mehrwertsteuer ist (:ref:`oxdaka03`, Pos. 1, 2).

Bei jeder Änderung des Landes wird die Mehrwertsteuer neu berechnet und die Meldung aktualisiert.


.. _oxdaka03:

.. figure:: /media/screenshots/oxdaka03.png
   :class: with-shadow
   :width: 650
   :alt: Bestellschritt 1 mit Hinweis auf Kundenstandort und MwSt.-Berechnung

   Abb.: Bestellschritt 1 mit Hinweis auf Kundenstandort und MwSt.-Berechnung

Was im Fehlerfall passiert
^^^^^^^^^^^^^^^^^^^^^^^^^^

Kommt ein Benutzer aus einem EU-Land, das Sie nicht für die Berechnung der Mehrwertsteuer für elektronische Dienstleistungen konfiguriert haben, erscheint eine Fehlermeldung.

Der Kunde wird aufgefordert den Artikel aus dem Warenkorb entfernen (:ref:`oxdaka04`, Pos. 1).

Grund: Die Mehrwertsteuer lässt sich nicht bestimmen  (:ref:`oxdaka04`, Pos. 2).

Um den Fehlerfall zu vermeiden, folgen Sie den Anweisungen unter

* :ref:`konfiguration:Artikel als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`
* :ref:`konfiguration:Kategorie als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`


Siehe auch: :ref:`erweiterung:Nicht kaufbare Artikel im Warenkorb hervorheben`.

.. _oxdaka04:

.. figure:: /media/screenshots/oxdaka04.png
   :class: with-shadow
   :width: 650
   :alt: Ermittlung der Mehrwertsteuer fehlgeschlagen

   Abb.: Ermittlung der Mehrwertsteuer fehlgeschlagen


Kompatibilität mit Zahlungsmodulen
----------------------------------

.. include:: /_static/reuse/payment-modules.rst

Sie müssen sicherstellen, dass Ihre Zahlungsmodule mit :productname:`OXID eShop eVAT` kompatibel sind.

Weitere Informationen finden Sie unter :ref:`konfiguration:Kompatibilität mit Zahlungsmodulen sicherstellen`.



.. Intern: oxdaka, Status: