Betrieb
=======

Nutzen Sie im laufenden Betrieb folgende Funktionen des Moduls :productname:`OXID eShop eVAT`:

* Kundenstandort in der Bestellung anzeigen
* Umsatzsteuer-Identifikationsnummer anzeigen
* Erweiterung der PDF-Rechnung nutzen

Kundenstandort in der Bestellung anzeigen
-----------------------------------------

.. todo: #HR: was ist der Anwendugsfall?
     Zitat: all telecommunications, radio and television broadcasting and electronically supplied services supplied to a non-taxable person are
            to be taxed in the Member State in which the customer is established, has his permanent address or usually resides, regardless of where
            the taxable person supplying those services is established. Most other services supplied to a non-taxable person continue to be taxed in
            the Member State in which the supplier is established.

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
   :scale: 100 %
   :alt: Kundenstandort in der Bestellung anzeigen

   Abb.: Kundenstandort in der Bestellung anzeigen


Umsatzsteuer-Identifikationsnummer anzeigen
-------------------------------------------

.. todo: #HR: was ist der Anwendugsfall? Ist das für B2B?  -- in der Einführung beschreiben wir den use case so: "für nichtsteuerpflichtige Kunden die Besteuerung von elektr. Artikeln integrieren"
         #HR: Was heißt: "Hinweis darauf geben, dass und ab wann der Kunde dem Shop gegenüber als steuerpflichtig anzusehen ist" -> eeehm keine Ahnung, sorry


Zeigen Sie die Umsatzsteuer-Identifikationsnummer eines Kunden sowie Datum und Zeit der Speicherung an.

Das Modul :productname:`OXID eShop eVAT` stellt sicher, dass die von einem Kunden eingegebene Umsatzsteuer-Identifikationsnummer (USt-IdNr.) zusammen mit Datum und Zeit gespeichert wird, wenn sie gültig ist.

USt-IdNr., Datum und Uhrzeit geben Ihnen einen Hinweis darauf, dass und ab wann der Kunde dem Shop gegenüber als steuerpflichtig anzusehen ist.

Der Kunde kann die Umsatzsteuer-Identifikationsnummer bei der Registrierung oder im Bestellprozess angeben. Er kann sie auch zu einem späteren Zeitpunkt in seinem Kundenkonto nachtragen.

|procedure|

1. Wählen Sie :menuselection:`Benutzer verwalten --> Benutzer`.
#. Wählen Sie den Benutzer.
#. Wählen Sie die Registerkarte :guilabel:`Stamm`.

|result|

Die Umsatzsteuer-Identifikationsnummer wird mit Datum und Zeit der Eingabe angezeigt (:ref:`oxdakd02`, Pos. 1).

.. _oxdakd02:

.. figure:: /media/screenshots/oxdakd02.png
   :scale: 100 %
   :alt: Umsatzsteuer-ID-Nr. anzeigen

   Abb.: Umsatzsteuer-ID-Nr. anzeigen


Erweiterung der PDF-Rechnung nutzen
-----------------------------------

Enthält eine Bestellung Artikel, welche als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gelten, fügt :productname:`OXID eShop eVAT` zusätzliche Informationen zur PDF-Rechnung hinzu.

Mit einem Sternchen :guilabel:`*` wird auf den verwendeten Mehrwertsteuersatz hingewiesen (:ref:`oxdakd03`, Pos. 1).

Eine Meldung informiert über das Land, dessen Mehrwertsteuersatz zur Berechnung des Artikelpreises herangezogen wurde (:ref:`oxdakd03`, Pos. 2).

.. _oxdakd03:

.. figure:: /media/screenshots/oxdakd03.png
   :scale: 100 %
   :alt: Hinweis auf Mehrwertsteuersatz in PDF-Rechnung

   Abb.: Hinweis auf Mehrwertsteuersatz in PDF-Rechnung


Mehrwertsteuersätze pflegen
---------------------------


Die aktuellen Mehrwertsteuersätze der verschiedenen Länder sind im Modul statisch hinterlegt. Sie werden nicht automatisch aktualisiert.

Sobald Sie :productname:`OXID eShop eVAT` aktiviert haben, müssen Sie als Shopbetreiber die Mehrwertsteuersätze pflegen.

.. tip::

   Um sich über mögliche Änderungen der Mehrwertsteuersätze auf dem Laufenden zu halten, abonnieren Sie einen Informationsservice.

|prerequisites|

Sie haben beim Konfigurieren sichergestellt, dass unter :menuselection:`Artikel verwalten --> Artikel --> <elektronisch erbrachte Dienstleistung> --> eVAT-Einstellungen` jedem betreffenden Artikel der für das jeweilige Land zutrefende Mehrwertsteuersatz zugeordnet ist.

Weitere Informationen finden Sie unter

* :ref:`konfiguration:Artikel als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`
* :ref:`konfiguration:Kategorie als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`

|procedure|

Pflegen Sie die Mehrwertsteuersätze unter :menuselection:`Stammdaten --> Länder --> <Land> --> MwSt.-Sätze`.



.. Intern: oxdakd, Status:

