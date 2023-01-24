Betrieb
=======

Nutzen Sie im laufenden Betrieb folgende Funktionen des Moduls :productname:`OXID eShop eVAT`:

* Kundenstandort in der Bestellung anzeigen
* Umsatzsteuer-Identifikationsnummer anzeigen
* Erweiterung der PDF-Rechnung nutzen

Kundenstandort in der Bestellung anzeigen
-----------------------------------------

Verifizieren Sie bei Bedarf, dass :productname:`OXID eShop eVAT` den Kundenstandort ermittelt hat.

|prerequisites|

Ihr Kunde hat mindestens einen Artikel gekauft, der als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gilt.

|procedure|

1. Wählen Sie :guilabel:`Bestellungen verwalten --> Bestellungen`.
2. Wählen Sie eine Bestellung, die einen elektronischen Artikel enthält.

|result|

Auf der Registerkarte :guilabel:`Stamm` wird am unteren Ende des Eingabebereichs das Ergebnis der Bestimmung des Kundenstandortes angezeigt (:ref:`oxdakd01`, Pos. 1).

.. _oxdakd01:

.. figure:: /media/screenshots/oxdakd01.png
   :class: with-shadow
   :width: 650
   :alt: Kundenstandort in der Bestellung anzeigen

   Abb.: Kundenstandort in der Bestellung anzeigen


Umsatzsteuer-Identifikationsnummer anzeigen
-------------------------------------------

Zeigen Sie bei Bedarf die Umsatzsteuer-Identifikationsnummer des Kunden sowie Datum und Zeit der Speicherung an.

Das Modul :productname:`OXID eShop eVAT` stellt sicher, dass die von einem Kunden eingegebene Umsatzsteuer-Identifikationsnummer (USt-IdNr.) zusammen mit Datum und Zeit gespeichert wird, wenn sie gültig ist.

.. todo: #SB/#Joe: was bedeutet " ab wann der Kunde dem Shop gegenüber als steuerpflichtig anzusehen ist"? -- Was könnte der rechtliche Anwendungsfall der Info sein? -- Huíntergrund ist ja: Auslandskunden mit USt-ID zahlen dem Shopbetreiber keine MWSt., sondern  den Nettopreis.
    Warum genau ist das Datum wichtig (ohne eVAT-Modul wird nur die USt-ID angezeigt).

USt-IdNr., Datum und Uhrzeit geben Ihnen einen Hinweis darauf, dass und ab wann der Kunde dem Shop gegenüber als steuerpflichtig anzusehen ist.

Der Kunde kann die Umsatzsteuer-Identifikationsnummer bei der Registrierung oder im Bestellprozess angeben. Er kann sie auch zu einem späteren Zeitpunkt in seinem Kundenkonto nachtragen.

|procedure|

1. Wählen Sie :menuselection:`Benutzer verwalten --> Benutzer`.
#. Wählen Sie den Benutzer.
#. Wählen Sie die Registerkarte :guilabel:`Stamm`.

|result|

Die Umsatzsteuer-Identifikationsnummer wird mit Datum und Zeit der Eingabe angezeigt (:ref:`oxdakd02`, Pos. 1).

.. todo: #HR: der Zeitstempel wird nicht (mehr) angezeigt) -- Bug, wird gefixt
.. todo: Bild neu machen DE/EN

.. _oxdakd02:

.. figure:: /media/screenshots/oxdakd02.png
   :width: 450
   :alt: Umsatzsteuer-ID-Nr. anzeigen

   Abb.: Umsatzsteuer-ID-Nr. anzeigen


Erweiterung der PDF-Rechnung nutzen
-----------------------------------

Enthält eine Bestellung Artikel, welche als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gelten, fügt :productname:`OXID eShop eVAT` zusätzliche Informationen zur PDF-Rechnung hinzu.

Mit einem Sternchen :guilabel:`*` wird auf den verwendeten Mehrwertsteuersatz hingewiesen (:ref:`oxdakd03`, Pos. 1).

Eine Meldung informiert über das Land, dessen Mehrwertsteuersatz zur Berechnung des Artikelpreises herangezogen wurde (:ref:`oxdakd03`, Pos. 2).

.. _oxdakd03:

.. figure:: /media/screenshots/oxdakd03.png
   :class: with-shadow
   :width: 650
   :alt: Hinweis auf Mehrwertsteuersatz in PDF-Rechnung

   Abb.: Hinweis auf Mehrwertsteuersatz in PDF-Rechnung


Mehrwertsteuersätze pflegen
---------------------------


Die aktuellen Mehrwertsteuersätze der verschiedenen Länder sind im Modul statisch hinterlegt. Sie werden nicht automatisch aktualisiert.

Sobald Sie :productname:`OXID eShop eVAT` aktiviert haben, müssen Sie als Shopbetreiber die Mehrwertsteuersätze pflegen.

.. tip::

   Um sich über mögliche Änderungen der Mehrwertsteuersätze auf dem Laufenden zu halten, abonnieren Sie einen Informationsservice.

|prerequisites|

Sie haben beim Konfigurieren sichergestellt, dass unter :menuselection:`Artikel verwalten --> Artikel --> <elektronisch erbrachte Dienstleistung> --> eVAT-Einstellungen` jedem betreffenden Artikel der für das jeweilige Land gültige Mehrwertsteuersatz zugeordnet ist.

Weitere Informationen finden Sie unter

* :ref:`configuration:Artikel als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`
* :ref:`configuration:Kategorie als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`

|procedure|

Pflegen Sie die Mehrwertsteuersätze unter :menuselection:`Stammdaten --> Länder --> <Land> --> MwSt.-Sätze`.



.. Intern: oxdakd, Status:

