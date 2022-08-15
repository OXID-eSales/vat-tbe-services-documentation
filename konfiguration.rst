Konfiguration
=============

Damit die Mehrwertsteuer für Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen berechnet werden kann, konfigurieren Sie das Modul eVAT.

Machen Sie das Modul :productname:`eVAT` für Ihren OXID eShop betriebsbereit.

Grundsätzliches Vorgehen
------------------------

1. Aktivieren Sie das Modul.
#. Ordnen Sie Ländern Mehrwertsteuersätze zu und aktivieren Sie die Länder für die Berechnung der spezifischen Mehrwertsteuer.
#. Kennzeichnen Sie Artikel oder Kategorien von Artikeln als elektronische Produkte oder Dienstleistungen.
#. Legen Sie die Methoden für die Bestimmung des Kundenstandortes fest.
#. Verifizieren Sie den Sitz des Shops.
#. Stellen Sie die Kompatibilität mit Zahlungsmodulen sicher.


eVAT aktivieren
---------------

Aktivieren Sie :productname:`eVAT` in jedem Subshop, in dem Sie das Modul nutzen wollen.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`. 
2. Wählen Sie das Modul :guilabel:`eVAT` und wählen Sie :menuselection:`Stamm --> Aktivieren`.




eVAT konfigurieren
------------------

.. todo:

Um die Konfiguration zu starten, wählen Sie :menuselection:`PayPal --> Konfiguration`.

Länderspezifische Mehrwertsteuersätze aktivieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Aktivieren Sie das Berechnen der Mehrwertsteuer für die betreffenden Länder. Prüfen Sie die hinterlegten Mehrwertsteuersätze und passen Sie sie bei Bedarf an.

.. attention::
   **Mehrwertsteuersätze als Shop-Betreiber pflegen**

   Mehrwertsteuersätze sind für die Länder der Europäischen Union bereits vorbereitet. Die Mehrwertsteuersätze sind im Modul statisch hinterlegt.

   .. todo: #HR: "Änderungen an den Werten müssen im Repository gepflegt werden." Betrieb: Wie pflege ich Änderungen im Repo? Wer macht es?

   Wenn Sie das Modul aktivieren, wird geprüft, ob es bereits einen Eintrag für das Land gibt:

   * Wenn ja, dann wird nichts gemacht.
   * Wenn nein, dann wird der Wert aus der Liste genommen

   .. todo: #HR: "Ist das Modul installiert, dann müssen Sie als Shop-Betreiber die Mehrwertsteuersätze pflegen." -- Meinen wir installiert oder aktiviert?

   Ist das Modul installiert, dann müssen Sie als Shop-Betreiber die Mehrwertsteuersätze pflegen.

   Weitere Informationen finden Sie unter :ref:`betrieb:Mehrwertsteuersätze pflegen`.


.. note::
   **OXID eShop Enterprise Edition**

   Bei einer Enterprise Edition wirken sich Anpassungen der Mehrwertsteuersätze auf alle Subhops/Mandanten aus.

|procedure|

1. Wählen Sie :menuselection:`Stammdaten --> Länder --> Stamm`.
#. Aktivieren Sie die Option :guilabel:`eVAT-Modul MwSt. anwenden` für diejenigen Länder, auf die Sie die EU-Richtlinie anwenden wollen.
#. Um die hinterlegten Mehrwertsteuersätze bei Bedarf anzupassen oder neue Mehrwertsteuersätze anzulegen, wählen Sie die :guilabel:`MwSt.-Sätze` (:ref:`oxdakb01`).
   |br|
   Die Mehrwertsteuersätze für die Länder der Europäischen Union sind bereits vorbereitet.
   |br|
   Ändern Sie sie bei Bedarf oder löschen Sie sie.
   |br|
   Legen Sie neue Mehrwertsteuersätze jeweils mit einem Namen, einem Prozentsatz und einer optionalen Beschreibung an.
#. Speichern Sie Ihre Einstellungen.

.. _oxdakb01:

.. figure:: /media/screenshots/oxdakb01.png
   :scale: 100 %
   :alt: Beispiel: Mehrwertsteuersätze für Deutschland

   Abb.: Beispiel: Mehrwertsteuersätze für Deutschland


Artikel als elektronisches Produkt oder Dienstleistung markieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Machen Sie Artikel, die zu den Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachten Dienstleistungen zählen, als solche kenntlich.

Alternativ: Markieren Sie alle Artikel einer Kategorie als elektronisches Produkt oder Dienstleistung (siehe :ref:`konfiguration:Kategorie als elektronisches Produkt oder Dienstleistung markieren`).

.. note::
   **OXID eShop Enterprise Edition**

   Bei einer Enterprise Edition können Sie nur die Artikel des Hauptshops anpassen.

.. todo: #HR: Was genau folgt daraus: "Bei einer Enterprise Edition können Sie nur die Artikel des Hauptshops anpassen."?


|procedure|

.. todo: #tbd: verifizieren:

1. Wählen Sie :menuselection:`Artikel verwalten --> Artikel`.
#. Wählen Sie die Registerkarte :guilabel:`eVAT-Einstellungen`.
#. Markieren Sie das Kontrollkästchen :guilabel:`Artikel ist eine Telekommunikations-, Rundfunk-, Fernseh- oder auf elektronischem Weg erbrachte Dienstleistung` (:ref:`oxdakb02`, Pos. 1).
#. Weisen Sie dem Artikel die gültigen Mehrwertsteuersätze für die einzelnen Länder zu (:ref:`oxdakb02`, Pos. 2).

#. Ergänzen Sie die Kundeninformationen zu den Mehrwertsteuersätzen.




.. _oxdakb02:

.. figure:: /media/screenshots/oxdakb02.png
   :scale: 100 %
   :alt: Mehrwertsteuersätze einem Artikel zuweisen

   Abb.: Reduzierten Mehrwertsteuersatz einem Artikel zuweisen


Kategorie als elektronisches Produkt oder Dienstleistung markieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Markieren Sie alle Artikel einer Kategorie als elektronische Produkte oder Dienstleistungen.

.. note::
   **Überschreiben von Artikel-individuellen eVAT-Einstellungen**

   Änderungen der eVAT-Einstellungen überschreiben alle individuellen eVAT-Einstellungen bei allen Artikeln dieser Kategorie.

|procedure|

.. todo: #tbd: verifizieren:

1. Wählen Sie :menuselection:`Artikel verwalten --> Kategorie`.
#. Wählen Sie die Registerkarte :guilabel:`eVAT-Einstellungen`.
#. Markieren Sie das Kontrollkästchen :guilabel:`Artikel in dieser Kategorie sind elektronische Dienstleistungen` (:ref:`oxdakb03`, Pos. 1).
#. Weisen Sie dem Artikel die gültigen Mehrwertsteuersätze für die einzelnen Länder zu.
#. Speichern Sie Ihre Einstellungen.

.. _oxdakb03:

.. figure:: /media/screenshots/oxdakb03.png
   :scale: 100 %
   :alt: Artikel einer Kategorie als elektronische Dienstleistungen definieren

   Abb.: Artikel einer Kategorie als elektronische Dienstleistungen definieren


Bestimmen des Kundenstandorts konfigurieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Aktivieren Sie die Methoden zum Bestimmen des Kundenstandorts.

Legen Sie eine Bestimmungsmethode als Standard fest.

|background|

Die EU-Durchführungsverordnung Nr. 1042/2013 schreibt vor, dass das Herkunftsland des Kunden ermittelt werden muss, der eine Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachten Dienstleistung bestellt, um die Mehrwertsteuer korrekt berechnen zu können.

Der Kundenstandort muss durch mindestens zwei Prüfungen festgestellt werden. Die alleinige Angabe des Kunden im Bestellprozess reicht nicht aus, Sie müssen die Angabe des Kunden prüfen.

.. todo: #HR: was bedeutet das Folgende genau? ("verfügt über eine Rolle...")

Das Modul eVAT verfügt über eine Regel, um das Herkunftsland eines Kunden herauszufinden sowie über die Möglichkeit, bei Bedarf eigene Bestimmungsmethoden hinzuzufügen.

.. todo: #HR: gemeint: eVAT verfügt über eine ** EINZIGE" Regel,.. -- und das ist die Methode Rechnunngsadresse?

Das Modul eVAT verwendet folgende Methoden, um den Kundenstandort zu bestimmen:

* die Rechnungsadresse des Kunden
* die sogenannte Geolocation

.. todo: #VL: Aussage ist falsch: Geolocation ist nicht implementiert, das Gesetz schreibt zwei Methoden vorgehen; Geolocation ist fake, eVAT ist nicht marktfertig: OXID haftet -- "wirschreiben derzit nur vorbereitet", das steht auch nicht in Readme

  Die Geolocation bestimmt den Standort basierend auf der IP-Adresse des zugehörigen Endgerätes.

  Die Bestimmungsmethode der Geolocation ist derzeit nur vorbereitet und muss noch implementiert werden.

.. todo: #HR: "Geolocation ist derzeit nur vorbereitet und muss noch implementiert werden": Was heißt dann "Das Modul eVAT verwendet zwei Bestimmungsmethoden, um den Kundenstandort zu bestimmen"?
         #HR: Sind die EU-Anforderungen aktuell nicht erfüllt?, siehe Michael: "Sofern das noch fertig gebaut wird,  wäre die Anforderung der EU zwei Checks der Angaben des Kunden durchzuführen erfüllt."

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`.
#. Wählen Sie das Modul :guilabel:`eVAT` und wählen Sie die Registerkarte :guilabel:`Einstell.`.
#. Aktivieren Sie unter :guilabel:`Bestimmungsmethode für Kundenstandort` die gewünschte Bestimmungsmethoden (:ref:`oxdakb04`, Pos. 1):
   |br|

      * Um den Kundenstandort mittels Rechnungsadresse zu prüfen, ordnen sie dem Parameter :technicalname:`billing_country` den Wert :technicalname:`1` zu.
      * Um den Kundenstandort mittels Geolocation zu prüfen, ordnen sie dem Parameter :technicalname:`geo_location` den Wert :technicalname:`1` zu.

.. todo: #HR: welchen Sinn hat es Geolocation zu aktivieren, wenn es nicht implementiert ist? -- löschen; welche Vorschrift gibes? Bestimmung, dass es mind 2 Methoden geben muss;


   .. code::

      billing_country => 1
      geo_location => 1

   Das Ergebnis der Prüfung wird in der Bestellung gespeichert.
   |br|
   Um eine Bestimmungsmethode zu deaktivieren, weisen Sie den Wert :technicalname:`0` zu.

#. Für den Fall, dass die Ergebnisse der Prüfungen einander widersprechen, legen Sie unter :guilabel:`Standardmethode für Kundenstandort` fest, welche Methode Vorrang haben soll (:ref:`oxdakb04`, Pos. 2).
   |br|
   Die Prüfung der Rechnungsadresse ist standardmäßig eingestellt.
   |br|
   Wenn Sie keine Bestimmungsmethode als Standard definieren oder die angegebene Bestimmungsmethode nicht gefunden wurde, wird die erste Bestimmungsmethode verwendet, die kein leeres Land als Ergebnis zurückgibt.
#. Speichern Sie Ihre Einstellungen.

.. todo: #HR: Wie wirkt sich die Einstellung "Sitz des Shops" in diesem Kontext aus? ist es auch eine Bestimmungsmethode?  -- siehe nächster Abschnitt

.. _oxdakb04:

.. figure:: /media/screenshots/oxdakb04.png
   :scale: 100 %
   :alt: Bestimmungsmethode konfigurieren

   Abb.: Methoden zur Bestimmung des Kundenstandorts konfigurieren

|result|

Im laufenden Betrieb können Sie das Ergebnis der Bestimmung des Kundenstandortes wird in der Bestellung prüfen (siehe :ref:`betrieb:Kundenstandort in der Bestellung anzeigen`).


Sitz des Shops verifizieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Stellen Sie sicher, dass der Sitz des Shops richtig konfiguriert ist.

|background|

Das System prüft, ob ein Kunde aus demselben Land kommt, in dem der Shop ansässig ist.

Ist das der Fall, wird der für den Shop als Standard definierte Mehrwertsteuersatz zur Berechnung des Warenwerts verwendet.

.. todo: #HR: 1. Was bedeutet im Folgenden: "als wäre kein Land eingetragen"? 2. Wie merkt das System, wenn der Code falsch ist?

Ist der Ländercode nicht korrekt, verhält sich der Shop so, als wäre kein Land eingetragen.

.. todo: #HR: Was heißt "Artikel ... werden nicht als elektr. Dienstl. gekennzeichnet"?

Artikel, welche Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen darstellen, werden nicht als solche gekennzeichnet.

.. todo: #HR: Was heißt: "Es werden auch keine damit in Zusammenhang stehenden Meldungen ausgegeben."

Es werden auch keine damit in Zusammenhang stehenden Meldungen ausgegeben.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`.
#. Wählen Sie das Modul :guilabel:`eVAT` und wählen Sie die Registerkarte :guilabel:`Einstell.`.
#. Tragen Sie im Feld :guilabel:`Sitz des Shops` den Ländercode für den Shop-Standort im ISO2-Format ein (:ref:`oxdakb04`, Pos. 3).



PDF-Rechnung konfigurieren
--------------------------

Wenn Sie in Ihrem OXID eShop :productname:`PDF-Rechnung` (siehe `github.com/OXIDprojects/pdf-invoice-module <https://github.com/OXIDprojects/pdf-invoice-module`_) verwenden, dann stellen Sie sicher, dass die Reihenfolge der überladenen Klassen stimmt.

.. todo: #HR: Was ist das auf EN: "overloaded" classes oder "extended" wie hier beschrieben: https://docs.oxid-esales.com/developer/en/latest/development/modules_components_themes/quality.html#extending-and-reusing-the-shop-functionality
         #HR: Michael schreibt: "Das Wort "überschreiben" wäre vermutlich eher richtiger als "überladen". Beides ist jedoch geläufig."

.. todo: VL: zu https://github.com/OXIDprojects/pdf-invoice-module: brauchen wir eine Doku? -- nein, nicht von Oxid entw.; nur Reihenfolge wichtig wie beschrieben

|procedure|

1. Wählen Sie im Administrationsbereich :menuselection:`Erweiterungen --> Module`.
   |br|
   Auf der Registerkarte :guilabel:`Installierte Shop-Module` werden die überladenen Klassen aufgelistet.
#. Stellen Sie sicher, dass unter :guilabel:`oxorder` das Modul :technicalname:`invoicepdf` vor dem Modul :technicalname:`oevattbe` platziert ist (wie in :ref:`oxdakb05`).
   |br|
   Ziehen Sie die Einträge mit der gedrückten Maustaste an die richtige Position.
#. Speichern Sie Ihre Einstellungen.

.. _oxdakb05:

.. figure:: /media/screenshots/oxdakb05.png
   :scale: 100 %
   :alt: Korrekte Reihenfolge der Module für die Klasse oxorder sicherstellen

   Abb.: Korrekte Reihenfolge der Module für die Klasse oxorder sicherstellen

Kundeninformationen zu Mehrwertsteuersätzen ergänzen
----------------------------------------------------

Informieren Sie Ihre Kunden über die verschiedenen Mehrwertsteuersätze.

Ihre Kunden gelangen zu diesen Informationen über einen Link auf der Artikeldetailseite (siehe :ref:`einfuehrung:Informationen zur Mehrwertsteuer aus Kundensicht`).

|procedure|

1. Wählen Sie im Administrationsbereich :menuselection:`Kundeninformationen `--> CMS-Seiten`.
#. Rufen Sie die Seite mit der ID :technicalname:`oxdeliveryinfo` auf.
#. Fügen Sie Informationen bezüglich der speziellen Artikel und der neuen Berechnung der Mehrwertsteuer hinzu.

.. todo: Beispiel für solche Ergänzungen angeben


Kompatibilität mit Zahlungsmodulen sicherstellen
------------------------------------------------

Wenn Sie zusätzliche Zahlungsmodule nutzen, stellen Sie sicher, dass Ihre Zahlungsmodule mit :productname:`eVAT` kompatibel sind.

Dazu prüfen Sie, ob Ihr Zahlungsmodul eine Schnellkauf-Funktion hat (das ist beispielsweise bei :productname:`PayPal` der Fall), und schalten die Schnellkauf-Funktion ab.

Sie müssen nichts tun, wenn Sie

* ein Zahlungsmodul ohne Schnellkauf-Funktion nutzen, beispielsweise :productname:`Unzer Payment für OXID`
* die mit :productname:`eVAT` kompatiblen Zahlungsmodule :productname:`PayPal Checkout` oder :productname:`Amazon Pay`, nutzen


|background|

.. include:: /_static/reuse/payment-modules.rst

|procedure|

In unserem folgenden Beispiel stellen Sie die Kompatibilität für das Zahlungsmodul :productname:`PayPal` sicher.

1. Wählen Sie :menuselection:`Erweiterungen --> Module`.
#. Wählen Sie das Zahlungsmodul, in unserem Beispiel :productname:`PayPal`.
#. Stellen Sie sicher, dass die Checkout-Seite angezeigt wird.
   |br|
   Dazu deaktivieren Sie in unserem Beispiel (für :productname:`PayPal`) auf der Registerkarte :guilabel:`Einstell.` das Kontrollkästchen :guilabel:`Bestellung nach PayPal Checkout abschließen` (:ref:`oxdakb06`, Pos. 1).
   |br|
   Ergebnis: Die Schnellkauf-Funktion ist abgeschaltet, Bestellungen werden nicht durch den Zahlungsdienstleister sofort abgeschlossen, sondern der Kunde landet auf der Checkout-Seite, und der Kunde muss die Bestellung mit der korrekt bestimmten Mehrwertsteuer bestätigen.
   |br|
   Weitere Informationen finden Sie in der Dokumentation Ihres Zahlungsmoduls.
#. Wenn Ihr Zahlungsmodul es nicht zulässt, die Schnellkauf-Funktion abzuschalten, dann deaktivieren Sie das Zahlungsmodul für die elektronischen Artikel.

.. todo: #HR: PayPal Plus: eine Doku: Heike fragen: wer ist Prod-Manager

.. _oxdakb06:

.. figure:: /media/screenshots/oxdakb06.png
   :scale: 100 %
   :alt: Schnellkauf-Funktion des Moduls abschalten

   Abb.: Schnellkauf-Funktion des Moduls :productname:`PayPal` abschalten

.. Intern: oxdakb, Status: