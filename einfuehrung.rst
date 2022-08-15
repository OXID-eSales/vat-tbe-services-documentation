Wofür/Wofür nicht?
==================

Integrieren Sie mit dem Modul :productname:`eVAT` für nichtsteuerpflichtige Kunden die Besteuerung von Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen in Ihren OXID eShop.


.. todo: #HR: wer ist Produkt-Manager?: Wenn el. Artikel, dann Modul nötig; hilft auch bei anderen Produkten, aber da nicht nötig; wenn business > 100000 Euro auch mit 19% nach Österreich; Jahresumsatz
   Große eShops: aus Österreich bestellt, dann 19 -> Modul würde helfen: wenn gezwungen, MWSt korrekt auszuweisen, dann Modul: Steuerberater fragen


Funktionsweise
--------------

:productname:`eVAT` passt die Berechnung der Mehrwertsteuer für Artikel an, mit denen Sie elektronisch erbrachten Dienstleistungen anbieten.

* Ein OXID eShop :emphasis:`ohne` das Modul :productname:`eVAT` verwendet immer den Mehrwertsteuersatz, den Sie im Administrationsbereich unter :menuselection:`Stammdaten --> Grundeinstellungen --> Einstell. --> Mehrwertsteuer` als Standard festgelegt haben.
* Ein OXID eShop :emphasis:`mit` dem Modul :productname:`eVAT` berechnet die Mehrwertsteuer für Artikel, die Sie in Ihrem OXID eShop als elektronische Produkte oder Dienstleistungen definiert haben, mit dem Mehrwertsteuersatz, der dem ermittelten Kundenstandort entspricht.
  |br|
  Für alle übrigen Artikel wird der Mehrwertsteuersatz herangezogen, der als Standard im Shop gilt.

Informationen zur Mehrwertsteuer aus Kundensicht
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Im Frontend werden alle Artikel, mit denen Sie elektronisch erbrachte Dienstleistungen anbieten, mit zwei Sternchen ** markiert (:ref:`oxdaka01`, Pos. 1).

Diese Markierung am Artikelpreis erscheint auf der Startseite, in der Kategorieansicht, der Detailseite des Artikels und an verschiedenen anderen Stellen.

.. _oxdaka01:

.. figure:: /media/screenshots/oxdaka01.png
   :scale: 100 %
   :alt: Auszeichnung elektronisch erbrachter Dienstleistungen: Beispiel Artikel-Detailansicht

   Abb.: Auszeichnung elektronisch erbrachter Dienstleistungen


Am unteren rechten Ende einer jeden Seite des Frontends weisen die zwei Sternchen :guilabel:`**` auf eine elektronisch erbrachte Dienstleistung hin (:ref:`oxdaka01`, Pos. 2).

Ein Link ruft die Seite auf, auf der Sie als Shopbetreiber Ihre Kunden detailliert über Zahlung und Lieferung Ihrer Ware informieren.

Den Inhalt dieser Seite bearbeiten Sie im Administrationsbereich unter :menuselection:`Kundeninformationen --> CMS-Seiten` (siehe :ref:`konfiguration:Kundeninformationen zu Mehrwertsteuersätzen ergänzen`).


Der Bestellprozess aus Kundensicht
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Legt Ihr Kunde einen Artikel, mit Sie elektronisch erbrachte Dienstleistungen anbieten, in den Warenkorb, dann werden die zwei Sternchen :guilabel:`**` bei der Mehrwertsteuer angezeigt (:ref:`oxdaka02`, Pos. 1).

Eine Meldung weist Ihren Kunden darauf hin, auf welchem Land die angezeigte Mehrwertsteuer basiert und dass sich diese ändern kann, sobald der Kunde im Shop angemeldet ist (:ref:`oxdaka02`, Pos. 2).

.. _oxdaka02:

.. figure:: /media/screenshots/oxdaka02.png
   :scale: 100 %
   :alt: Bestellschritt 1 mit Hinweis auf MwSt.-Berechnung

   Abb.: Bestellschritt 1 mit Hinweis auf MwSt.-Berechnung


Die Mehrwertsteuer wird nach Anmeldung oder nach Angeben der Rechnungsadresse berechnet, nachdem der Kundenstandort durch die definierten Bestimmungsmethoden ermittelt wurde (siehe :ref:`konfiguration:Bestimmen des Kundenstandorts konfigurieren`).

Eine Meldung weist den Kunden erneut darauf hin, welches Land Grundlage für die Berechnung der Mehrwertsteuer ist (:ref:`oxdaka02`, Pos. 1, 2).

Bei jeder Änderung des Landes wird die Mehrwertsteuer neu berechnet und die Meldung aktualisiert.

.. todo: #HR: Was folgt aus der Fehlermeldung für den Kunden und für den Shopbetreiber?: "Kommt ein Benutzer aus einem EU-Land, das nicht für die neue Berechnung der Mehrwertsteuer konfiguriert ist, wird eine Fehlermeldung ausgegeben. Die Bestellung kann dennoch fortgesetzt werden."
              sieht nach Info aus, Bestellung kann aber durchgeführt werden. Screenshot oxdaka03 sieht nciht nach Fehlermeldung aus ?

Kommt ein Benutzer aus einem EU-Land, das nicht für die neue Berechnung der Mehrwertsteuer konfiguriert ist, wird eine Fehlermeldung ausgegeben. Die Bestellung kann dennoch fortgesetzt werden.

.. _oxdaka03:

.. figure:: /media/screenshots/oxdaka03.png
   :scale: 100 %
   :alt: Bestellschritt 1 mit Hinweis auf Kundenstandort und MwSt.-Berechnung

   Abb.: Bestellschritt 1 mit Hinweis auf Kundenstandort und MwSt.-Berechnung




Kompatibilität mit Zahlungsmodulen
----------------------------------

.. include:: /_static/reuse/payment-modules.rst

Sie müssen sicherstellen, dass Ihre Zahlungsmodule mit :productname:`eVAT` kompatibel sind.

Weitere Informationen finden Sie unter :ref:`konfiguration:Kompatibilität mit Zahlungsmodulen sicherstellen`.



Gesetzliche Grundlage
---------------------

Mit dem Modul :productname:`eVAT` stellen Sie sicher, dass Sie die EU-Durchführungsverordnung Nr. 1042/2013 bezüglich des Orts der Dienstleistung einhalten.

Diese EU-Durchführungsverordnung besagt, dass Händler und Dienstleister ab dem 1. Januar 2015 beim Verkauf ihrer elektronisch erbrachten Dienstleistungen die Mehrwertsteuer des EU-Landes abführen müssen, aus dem der Käufer kommt. Vorher war es die Mehrwertsteuer des Landes, in dem das eigene Unternehmen ansässig ist.

Weitere Informationen finden Sie auf den Seiten der Europäischen Kommission unter: `ec.europa.eu/taxation_customs/news/vat-updated-version-moss-report-has-just-been-published-2016-05-12_de <https://ec.europa.eu/taxation_customs/news/vat-updated-version-moss-report-has-just-been-published-2016-05-12_de>`_.

Technische Umsetzung
--------------------

Artikel, die Sie in Ihrem OXID eShop als elektronisch erbrachte Dienstleistungen definieren, sind beim Kauf als solche gekennzeichnet.

Das System ermittelt das Herkunftsland des privaten Käufers (B2C) nach festgelegten Regeln und berechnet entsprechend die jeweilige Mehrwertsteuer.

Alle der Berechnung zugrunde liegenden Daten werden bei der Bestellung gespeichert.

Ihre Vorteile
-------------

* Definieren Sie Artikel als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen.
* Aktivieren Sie Artikel einzeln oder kategorieweise als elektronische Produkte oder Dienstleistungen und ordnen Sie die Mehrwertsteuersätze für gewünschte Länder zu.
* Nutzen Sie

  * vorbereitete Mehrwertsteuersätze für alle Länder der Europäischen Union
  * die Bestimmung des Kundenstandortes nach definierten Bestimmungsmethoden
  * die Protokollierung des Kundenstandortes bei Bestellungen von elektronischen Produkten oder Dienstleistungen
  * die Speicherung der USt-ID-Nummer mit Datum und Uhrzeit als Nachweis steuerpflichtiger Kunden
* Erweitern Sie :productname:`eVAT` bei Bedarf um eigene Bestimmungsmethoden



.. Intern: oxdaka, Status: