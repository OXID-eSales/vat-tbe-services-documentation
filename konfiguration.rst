Konfiguration
=============

Damit die Mehrwertsteuer für Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen berechnet werden kann, konfigurieren Sie das Modul eVAT.

Machen Sie das Modul :productname:`OXID eShop eVAT` für Ihren OXID eShop betriebsbereit.

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

Aktivieren Sie :productname:`OXID eShop eVAT` in jedem Subshop, in dem Sie das Modul nutzen wollen.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`. 
2. Wählen Sie das Modul :guilabel:`eVAT` und wählen Sie :menuselection:`Stamm --> Aktivieren`.

eVAT konfigurieren
------------------


Länderspezifische Mehrwertsteuersätze aktivieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Aktivieren Sie das Berechnen der Mehrwertsteuer für die betreffenden Länder.

Prüfen Sie die hinterlegten Mehrwertsteuersätze und passen Sie sie bei Bedarf an.

.. attention::
   **Mehrwertsteuersätze als Shop-Betreiber pflegen**

   Mehrwertsteuersätze sind für die Länder der Europäischen Union bereits vorbereitet.

   Die Mehrwertsteuersätze sind im Modul statisch hinterlegt, sie werden nicht automatisch angepasst.

   Wenn Sie das Modul aktivieren, wird geprüft, ob es bereits einen Eintrag für das Land gibt:

   * Wenn ja, dann wird nichts gemacht.
   * Wenn nein, dann wird der Wert aus der Liste genommen

   Ist das Modul aktiviert, dann müssen Sie als Shop-Betreiber die Mehrwertsteuersätze pflegen.

   Weitere Informationen finden Sie unter :ref:`betrieb:Mehrwertsteuersätze pflegen`.


.. note::
   **OXID eShop Enterprise Edition**

   Bei einer Enterprise Edition wirken sich Anpassungen der Mehrwertsteuersätze auf alle Subhops/Mandanten aus.

|procedure|

1. Wählen Sie :menuselection:`Stammdaten --> Länder`.
#. Markieren Sie das Land, auf das Sie die EU-Richtlinie anwenden wollen, und wählen Sie :guilabel:`Stamm`.
#. Aktivieren Sie die Option :guilabel:`eVAT-Modul MwSt. anwenden` (:ref:`oxdakb01a`).

   .. _oxdakb01a:

   .. figure:: /media/screenshots/oxdakb01a.png
      :scale: 100 %
      :alt: eVAT-Modul MwSt. anwenden

      Abb.: eVAT-Modul MwSt. anwenden

#. Um die hinterlegten Mehrwertsteuersätze bei Bedarf anzupassen oder neue Mehrwertsteuersätze anzulegen, wählen Sie die :guilabel:`MwSt.-Sätze` (:ref:`oxdakb01`, Pos. 1).
   |br|
   Die Mehrwertsteuersätze für die Länder der Europäischen Union sind bereits vorbereitet.
   |br|
   Passen Sie sie bei Bedarf an die aktuellen Bestimmungen an oder löschen Sie sie.
   |br|
   Bei Bedarf: Legen Sie unter :guilabel:`Neuen MwSt.-Satz anlegen` neue Mehrwertsteuersätze jeweils mit einem Namen, einem Prozentsatz und einer optionalen Beschreibung an.
   |br|
   Beispiel: Für das Vereinigte Königreich ergänzen Sie den 2022 geltenden Nullsatz unter anderem für gedruckte Bücher und Zeitungen sowie Hörbücher für Blinde (:ref:`oxdakb01`, Pos. 2).

   .. _oxdakb01:

   .. figure:: /media/screenshots/oxdakb01.png
      :scale: 100 %
      :alt: Mehrwertsteuersätze anpassen, Beispiel Vereinigtes Königreich

      Abb.: Mehrwertsteuersätze anpassen, Beispiel Vereinigtes Königreich

#. Speichern Sie Ihre Einstellungen.

Artikel als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Machen Sie Artikel, die zu den Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachten Dienstleistungen zählen, als solche kenntlich.

Alternativ: Markieren Sie alle Artikel einer Kategorie als elektronisches Produkt oder Dienstleistung (siehe :ref:`konfiguration:Kategorie als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen`).

.. note::
   **OXID eShop Enterprise Edition**

   Bei einer Enterprise Edition können Sie nur die Artikel des Elternshops anpassen. Die Eigenschaft eines elektronischen Produkts oder Dienstleistung wird an die Subshops vererbt.

   Artikel oder Kategorien, die Sie in einem Subshop neu anlegen, können Sie gesondert als elektronische Dienstleistungen markieren.

|procedure|

1. Wählen Sie :menuselection:`Artikel verwalten --> Artikel`.
#. Wählen Sie die Registerkarte :guilabel:`eVAT-Einstellungen`.
#. Markieren Sie das Kontrollkästchen :guilabel:`Artikel ist eine Telekommunikations-, Rundfunk-, Fernseh- oder auf elektronischem Weg erbrachte Dienstleistung` (:ref:`oxdakb02`, Pos. 1).
#. Weisen Sie dem Artikel die gültigen Mehrwertsteuersätze für die einzelnen Länder zu.
   |br|
   Ein eBook hat beispielsweise im Vereinigten Königreich den Normalsatz, in Frankreich den ermäßigten Satz 1 (:ref:`oxdakb02`, Pos. 2).

   .. attention::

      **Konversion gefährdet**

      Fehlt die Zuordnung des Mehrwertsteuersatzes für ein Land, muss der Kunde den betreffenden Artikel aus dem Warenkorb entfernen.

      In unserem Beispiel (:ref:`einfuehrung:Was im Fehlerfall passiert`) kann ein Kunde aus Österreich das eBook nicht kaufen und erhält eine entsprechende Meldung.


.. _oxdakb02:

.. figure:: /media/screenshots/oxdakb02.png
   :scale: 100 %
   :alt: Mehrwertsteuersätze einem Artikel zuweisen

   Abb.: Mehrwertsteuersätze einem Artikel zuweisen


Kategorie als elektronisches Produkt markieren und Mehrwertsteuersatz zuordnen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Markieren Sie alle Artikel einer Kategorie als elektronische Produkte oder Dienstleistungen.

.. important::
   **Überschreiben von Artikel-individuellen eVAT-Einstellungen**

   Änderungen der eVAT-Einstellungen überschreiben alle individuellen eVAT-Einstellungen bei allen Artikeln dieser Kategorie.



|procedure|

1. Wählen Sie :menuselection:`Artikel verwalten --> Kategorien`.
#. Wählen Sie die Produktkategorie.
#. Wählen Sie die Registerkarte :guilabel:`eVAT-Einstellungen`.
#. Markieren Sie das Kontrollkästchen :guilabel:`Artikel in dieser Kategorie sind elektronische Dienstleistungen` (:ref:`oxdakb03`, Pos. 1).
#. Weisen Sie dem Artikel die gültigen Mehrwertsteuersätze für die einzelnen Länder zu (:ref:`oxdakb03`, Pos. 2).

   .. attention::

      **Konversion gefährdet**

      Fehlt die Zuordnung des Mehrwertsteuersatzes für ein Land, muss der Kunde den betreffenden Artikel aus dem Warenkorb entfernen.

      In unserem Beispiel (:ref:`einfuehrung:Was im Fehlerfall passiert`) kann ein Kunde aus Österreich das eBook nicht kaufen und erhält eine entsprechende Meldung.

#. Speichern Sie Ihre Einstellungen.

.. _oxdakb03:

.. figure:: /media/screenshots/oxdakb03.png
   :scale: 100 %
   :alt: Artikel einer Kategorie als elektronische Dienstleistungen definieren

   Abb.: Artikel einer Kategorie als elektronische Dienstleistungen definieren



Bestimmen des Kundenstandorts konfigurieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Aktivieren Sie das Bestimmen des Kundenstandorts.


|background|

Die EU-Durchführungsverordnung Nr. 1042/2013 schreibt vor, dass das Herkunftsland des Kunden ermittelt werden muss, der eine Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachten Dienstleistung bestellt, um die Mehrwertsteuer korrekt berechnen zu können.

Der Kundenstandort muss durch mindestens zwei Prüfungen festgestellt werden. Die alleinige Angabe des Kunden im Bestellprozess reicht nicht aus, Sie müssen die Angabe des Kunden prüfen.

.. todo: #Joe prüfen: a) Ist die rechtliche Anforderung valide, b) erfüllen wir sie?: "Die alleinige Angabe des Kunden im Bestellprozess reicht nicht aus, Sie müssen die Angabe des Kunden prüfen."
    Der Kunde gibt im Bestellprozess seine Rechnungsadresse an. Das Modul prüft die Rechnungsadresse. Wir haben also nur 1 Bestimmungsmethode.

.. todo: #Joe: Prüfen: Brauchen wir das countryVAT-Modul als 2. Methode, können wir es nutzen, um die rechtliche Anforderung zu erfüllen?

Das Modul :productname:`OXID eShop eVAT` verwendet die Rechnungsadresse des Kunden, um den Kundenstandort zu bestimmen.

Sie können bei Bedarf eigene Bestimmungsmethoden hinzuzufügen (siehe :ref:`erweiterung:Bestimmungsmethode für Kundenstandort hinzufügen`).


|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`.
#. Wählen Sie das Modul :guilabel:`OXID eShop eVAT` und wählen Sie die Registerkarte :guilabel:`Einstell.`.
#. Stellen Sie unter :guilabel:`Bestimmungsmethode für Kundenstandort` sicher, dass die Bestimmungsmethode :guilabel:`Kundenstandort mittels Rechnungsadresse ermitteln` aktiviert ist.
   |br|
   Dazu tun Sie folgendes:

   a. Stellen Sie sicher, dass dem Parameter :technicalname:`billing_country` der Wert :technicalname:`1` zugeordnet ist (:ref:`oxdakb04`, Pos. 1).

   .. code::

      billing_country => 1

   b. Stellen Sie sicher, dass :code:`billing_country` als Standard-Bestimmungsmethode gewählt ist (:ref:`oxdakb04`, Pos. 2).

   .. _oxdakb04:

   .. figure:: /media/screenshots/oxdakb04.png
         :scale: 100 %
         :alt: Bestimmungsmethode konfigurieren

         Abb.: Bestimmungsmethode konfigurieren

   .. note::

      Die Bestimmungsmethode Geolocation ist nicht implementiert.

      .. todo: #HR: Können wir Geolocation deaktivieren, so dass es nicht standardmäßig in dem Feld erscheint? -- kommt weg oder --> 0

#. Speichern Sie Ihre Einstellungen.


|result|

Das Ergebnis der Prüfung wird in der Bestellung gespeichert.

Im laufenden Betrieb können Sie das Ergebnis der Bestimmung des Kundenstandortes in der Bestellung prüfen (siehe :ref:`betrieb:Kundenstandort in der Bestellung anzeigen`).


Sitz des Shops verifizieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Stellen Sie sicher, dass der Sitz des Shops richtig konfiguriert ist.

.. todo: #HR: Das folgende stimmt nicht: keine oder falsche Landeskennung hat keine Auswirkung; was ist das erwartete Verhalten?


    |background|

    Das System prüft, ob ein Kunde aus demselben Land kommt, in dem der Shop ansässig ist.

    Ist das der Fall, wird der für den Shop als Standard definierte Mehrwertsteuersatz zur Berechnung des Warenwerts verwendet.

    Wenn Sie einen ungültigen Ländercode eintragen, verhält sich der Shop so, als wäre kein Land eingetragen.

    Artikel, welche Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen darstellen, werden dann nicht als solche gekennzeichnet.

    Es werden auch keine damit in Zusammenhang stehenden Meldungen ausgegeben.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`.
#. Wählen Sie das Modul :guilabel:`eVAT` und wählen Sie die Registerkarte :guilabel:`Einstell.`.
#. Tragen Sie im Feld :guilabel:`Sitz des Shops` den Ländercode für den Shop-Standort im ISO2-Format ein (in unserem Beispiel :code:`de` für Deutschland: :ref:`oxdakb04`, Pos. 3).


PDF-Rechnung konfigurieren
--------------------------

Wenn Sie in Ihrem OXID eShop :productname:`PDF-Rechnung` (siehe `github.com/OXIDprojects/pdf-invoice-module <https://github.com/OXIDprojects/pdf-invoice-module>`_) verwenden, dann stellen Sie sicher, dass die Reihenfolge der überladenen Klassen stimmt.

|procedure|

1. Wählen Sie im Administrationsbereich :menuselection:`Erweiterungen --> Module`.
   |br|
   Auf der Registerkarte :guilabel:`Installierte Shop-Module` werden die überladenen Klassen aufgelistet.
#. Stellen Sie sicher, dass unter :guilabel:`OxidEsales\Eshop\Application\Model\Order` das Modul :technicalname:`invoicepdfoxorder` vor dem Modul :technicalname:`oevattbeoxorder` platziert ist (:ref:`oxdakb05`, Pos. 1).
   |br|
   Ziehen Sie dazu den Eintrag mit gedrückter Maustaste an die richtige Position.
#. Speichern Sie Ihre Einstellungen.

.. _oxdakb05:

.. figure:: /media/screenshots/oxdakb05.png
   :scale: 100 %
   :alt: Korrekte Reihenfolge der Module sicherstellen

   Abb.: Korrekte Reihenfolge der Module sicherstellen

|result|

Sie können Rechnungen im PDF-Format ausgeben unter :menuselection:`Bestellungen verwalten --> Bestellungen --> <Bestellung> --> Übersicht`.

Kundeninformationen zu Mehrwertsteuersätzen ergänzen
----------------------------------------------------

Informieren Sie Ihre Kunden über die verschiedenen Mehrwertsteuersätze.

Ihre Kunden gelangen zu diesen Informationen über einen Link auf der Artikeldetailseite (siehe :ref:`einfuehrung:Informationen zur Mehrwertsteuer aus Kundensicht`, Pos. 2).

|procedure|

1. Wählen Sie im Administrationsbereich :menuselection:`Kundeninformationen --> CMS-Seiten`.
#. Rufen Sie die Seite mit der ID :technicalname:`oxdeliveryinfo` auf.
#. Fügen Sie Informationen bezüglich der speziellen Artikel und der neuen Berechnung der Mehrwertsteuer hinzu (:ref:`oxdakb05a`).
#. Speichern Sie Ihre Einstellungen.


.. _oxdakb05a:

.. figure:: /media/screenshots/oxdakb05a.png
   :scale: 100 %
   :alt: Kundeninformation zur Mehrwertsteuer ergänzen

   Abb.: Kundeninformation zur Mehrwertsteuer ergänzen


Kompatibilität mit Zahlungsmodulen sicherstellen
------------------------------------------------

Wenn Sie zusätzliche Zahlungsmodule nutzen, stellen Sie sicher, dass Ihre Zahlungsmodule mit :productname:`OXID eShop eVAT` kompatibel sind.

Dazu prüfen Sie, ob Ihr Zahlungsmodul eine Schnellkauf-Funktion hat (das ist beispielsweise bei :productname:`PayPal` der Fall), und schalten die Schnellkauf-Funktion ab.

Sie müssen nichts tun, wenn Sie

* ein Zahlungsmodul ohne Schnellkauf-Funktion nutzen, beispielsweise :productname:`Unzer Payment für OXID`
* die mit :productname:`OXID eShop eVAT` kompatiblen Zahlungsmodule :productname:`PayPal Checkout` oder :productname:`Amazon Pay`, nutzen


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

.. todo: #VL: PayPal Plus: eine Doku: Heike fragen: wer ist Prod-Manager -> gute Frage, Vilma fragen :D. Ansonsten interessant, sollte man mal ausprobieren, ob das wirklich mit dem bisherigen PayPal-Modul mit shop 6.5.x noch so funktioniert. Und was ist dann mit checkout über GraphQL?

.. _oxdakb06:

.. figure:: /media/screenshots/oxdakb06.png
   :scale: 100 %
   :alt: Schnellkauf-Funktion des Moduls abschalten

   Abb.: Schnellkauf-Funktion des Moduls :productname:`PayPal` abschalten

.. Intern: oxdakb, Status: