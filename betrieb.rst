Betrieb
=======

Nutzen Sie im laufenden Betrieb folgende Funktionen des Moduls :productname:`eVAT`:

* Kundenstandort in der Bestellung anzeigen
* Umsatzsteuer-Identifikationsnummer anzeigen
* Erweiterung der PDF-Rechnung nutzen

.. todo: #HR: Reden wir einheitlich eher von USt oder von MWSt?

Kundenstandort in der Bestellung anzeigen
-----------------------------------------

.. todo: #HR: was ist der Anwendugsfall?

Zeigen Sie die Information zum Kundenstandort in der Bestellung an.

|prerequisites|

Ihr Kunde hat mindestens einen Artikel gekauft, der als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gilt.

|procedure|

1. Wählen Sie :guilabel:`Bestellungen verwalten --> Bestellungen`.
2. Wählen Sie eine Bestellung, die einen elektronischen Artikel enthält.

|result|

Auf der Registerkarte :guilabel:`Stamm` wird am unteren Ende des Eingabebereichs eine Tabelle mit den Ergebnissen der Bestimmung des Kundenstandortes angezeigt (:ref:`oxdakd01`).

.. _oxdakd01:

.. figure:: /media/screenshots/oxdakd01.png
   :scale: 100 %
   :alt: Kundenstandort in der Bestellung anzeigen

   Abb.: Kundenstandort in der Bestellung anzeigen

In unserem Beispiel (:ref:`oxdakd01`) wurden zwei Bestimmungsmethoden verwendet.

Die Prüfung ergab, dass der deutsche Mehrwertsteuersatz für die Berechnung des Artikelpreises angewendet wird.

Die Bestimmung des Kundenstandorts mittels Geolocation lieferte kein Ergebnis.

.. todo: #HR: "Die Bestimmung des Kundenstandorts mittels Geolocation lieferte kein Ergebnis." -- da nicht implementiert?

.. note::

   Die Bestimmung des Kundenstandorts hängt von Ihrer Konfiguration ab.

   Weitere Informationen finden Sie unter :ref:`konfiguration:Bestimmen des Kundenstandorts konfigurieren`.

Umsatzsteuer-Identifikationsnummer anzeigen
-------------------------------------------

.. todo: #HR: was ist der Anwendugsfall? Ist das für B2B?  -- in der Einführung beschreiben wir den use case so: "für nichtsteuerpflichtige Kunden die Besteuerung von elektr. Artikeln integrieren"
         #HR: Was heißt: "Hinweis darauf geben, dass und ab wann der Kunde dem Shop gegenüber als steuerpflichtig anzusehen ist"


Zeigen Sie die Umsatzsteuer-Identifikationsnummer eines Kunden sowie Datum und Zeit der Speicherung an.

Das Modul :productname:`eVAT` stellt sicher, dass die von einem Kunden eingegebene Umsatzsteuer-Identifikationsnummer (USt-IdNr.) zusammen mit Datum und Zeit gespeichert wird, wenn sie gültig ist.

USt-IdNr., Datum und Uhrzeit sollen dem Shopbetreiber einen Hinweis darauf geben, dass und ab wann der Kunde dem Shop gegenüber als steuerpflichtig anzusehen ist.

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

Enthält eine Bestellung Artikel, welche als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gelten, fügt :productname:`eVAT` zusätzliche Informationen zur PDF-Rechnung hinzu.

Mit einem Sternchen :guilabel:`*` wird auf den verwendeten Mehrwertsteuersatz hingewiesen.

Eine Meldung informiert über das Land, dessen Mehrwertsteuersatz zur Berechnung des Artikelpreises herangezogen wurde.


Mehrwertsteuersätze pflegen
---------------------------

.. todo: #HR: verifizieren:

Die aktuellen Mehrwertsteuersätze der verschiedenen Länder sind im Modul statisch hinterlegt.

Sobald Sie :productname:`eVAT` installiert haben, müssen Sie als Shopbetreiber die Mehrwertsteuersätze pflegen.

.. todo: #HR: Wie halte ich mich über Änderungen auf dem laufenden?
         #HR: Wie pflege ich die Mehrwertsteuersätze?
         #HR: Meinen wir installiert oder aktiviert?




.. Intern: oxdakd, Status:

