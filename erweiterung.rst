Modul-Erweiterung
=================

Erweitern Sie das Modul :productname:`eVAT` bei Bedarf.

Wir beschreiben beispielhaft,

* wie Sie eine eigene Bestimmungsmethode für den Kundenstandort hinzufügen
* wie Sie einen Artikel im Warenkorb farblich hervorheben können, dessen Mehrwertsteuersatz nicht ermittelt werden konnte.

.. todo #HR: "wie Sie einen Artikel im Warenkorb markieren können": automatisch markieren? -> ja, das soll der Shop automatisch anzeigen


Bestimmungsmethode für Kundenstandort hinzufügen
------------------------------------------------

Um eine eigene Bestimmungsmethode für den Kundenstandort hinzuzufügen, erstellen Sie eine Klasse und registrieren sie.

Ein Beispielmodul finden Sie im Verzeichnis :file:`/documentation/countryEvidenceExampleModule` des Installationspakets.

.. todo: #HR: Was bdeutet der Hinweis im Klartext? Wer muss in welchem Fall was tun? -> der Shopbetreiber muss das e-vat Modul mit einem eigenen Modul erweitern.

.. note::

   Die Klasse :technicalname:`oeVATTBEGeoLocationEvidence` ist derzeit nur vorbereitet und muss implementiert werden.

   Das kann durch Erweitern dieser Klasse mit einem Modul und Implementierung der Methode :technicalname:`oeVATTBEGeoLocationEvidence::getCountryId()` umgesetzt werden.


|procedure|

Tun Sie Folgendes:

.. todo: #HR: Checkliste so OK? Ist eine Reihenfolge zu beachten? -> sollte passen, neues Modul schreiben und dann installieren, so ist das wohl gemeint

* Damit die neue Klasse eine Schnittstelle hat, stellen Sie sicher, dass sie die Klasse :technicalname:`oeVATTBEEvidence` erweitert.
* Registrieren Sie die Klasse mit :technicalname:`oeVATTBEEvidenceRegister::registerEvidence()`.
* Wenn die Klasse nicht mehr benötigt wird, beenden Sie die Registrierung der Klasse mit :technicalname:`oeVATTBEEvidenceRegister::unregisterEvidence()`.
* Erstellen Sie ein Modul, das die neue Klasse enthält.
* Tragen Sie die Klasse in der Datei :technicalname:`metadata.php` des Moduls ein.
* Verwenden Sie für das Registrieren und Abmelden der Klasse die Ereignisse :technicalname:`onActivate()` und :technicalname:`onDeactivate()` des Moduls.

  .. code::

     public static function onActivate()
        {
            if (class_exists('oeVATTBEEvidenceRegister')) {
                $oConfig = oxRegistry::getConfig();
                /** @var oeVATTBEEvidenceRegister $oEvidenceRegister */
                $oEvidenceRegister = oxNew('oeVATTBEEvidenceRegister', $oConfig);
                $oEvidenceRegister->registerEvidence('oeVATTBEExtendedEvidence1');
                $oEvidenceRegister->registerEvidence('oeVATTBEExtendedEvidence2');
            }
        }

        public static function onDeactivate()
        {
            if (class_exists('oeVATTBEEvidenceRegister')) {
                $oConfig = oxRegistry::getConfig();
                /** @var oeVATTBEEvidenceRegister $oEvidenceRegister */
                $oEvidenceRegister = oxNew('oeVATTBEEvidenceRegister', $oConfig);
                $oEvidenceRegister->unregisterEvidence('oeVATTBEExtendedEvidence1');
                $oEvidenceRegister->unregisterEvidence('oeVATTBEExtendedEvidence2');
            }
        }

  Falls das Modul die neue Klasse bei einer Deaktivierung nicht abgemeldet hat, werden die hinzugefügten Bestimmungsmethoden bei der nächsten Bestimmung des Kundenstandortes entfernt.

* Aktivieren Sie Ihr Modul mit den zusätzlichen Bestimmungsmethoden nur dann, wenn das Modul :productname:`eVAT` aktiv ist.

  Andernfalls wird :technicalname:`oeVATTBEEvidenceRegister` nicht gefunden.


Nicht kaufbare Artikel im Warenkorb hervorheben
-----------------------------------------------

Sie wollen nicht kaufbare Artikel im Warenkorb farblich hervorheben.

Das setzen Sie mit Hilfe einer CSS-Klasse um, die Sie in das Template :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl` integrieren.

Die Information, ob ein Artikel im Warenkorb kaufbar ist, liefert Ihnen die Controller-Methode :technicalname:`isOeVATTBETBEArticleValid`.

|background|

In einigen Fällen kann es sein, dass ein Artikel nicht gekauft werden kann, weil sich seine Mehrwertsteuer nicht berechnen lässt.

Ein Beispiel ist der Kauf eines Artikels, welcher als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gilt.

Fehlen die Mehrwertsteuersätze bei dem Land, aus dem der Kunde bestellen möchte, kommt es zum Fehler.

.. todo: #HR: "Fehlen die Mehrwertsteuersätze bei dem Land, aus dem der Kunde bestellen möchte, kommt es zum Fehler. " : Dient eVAT nicht gerade dazu, diesen Fall auszuschließen, indem ich die Artikel markiere und den Ländern USt-Sätze zuweise? Ist das nicht ein Konfig-Fehler?
-> wir haben ja inzwischen noch das geo-blocking Modul. Vermutlich ist der 'Fehler' einfach die Fehlermeldung, wenn das betreffende Land nicht konfiguriert wurde. Dh der Shop-Admin muss das entsprechen eintragen.

Es wird normalerweise eine Fehlermeldung mit Hinweis auf den betreffenden Artikel angezeigt. Der Kunde muss den Artikel aus dem Warenkorb entfernen.

Durch die farbliche Hervorhebung kann Ihr Kunde den betreffenden Artikel leichter identifizieren.

|procedure|

.. todo: #HR: Was genau tue ich hier?: -> offenbar ein neues Modul schreiben

1. CCS-Klasse erstellen und in Template :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl` integrieren?

.. todo: #HR: Die CSS-Klasse ist ja oeVATTBEBasketItemInvalid, die Funktion ist neuer Teil von Template :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl`

   .. code::

      [{foreach key=basketindex from=$oxcmp_basket->getContents() item=basketitem name=basketContents}]
            [{block name="checkout_basketcontents_basketitem"}]
             ....
            <tr class="basketItem
             [{if !$oView->isOeVATTBETBEArticleValid()}] oeVATTBEBasketItemInvalid[{/if}]"
             id="cartItem_[{$smarty.foreach.basketContents.iteration}]">

2. Fügen Sie die CSS-Klasse der CSS-Datei :technicalname:`/oe/oevattbe/out/src/css/vattbe.css` oder der CSS-Datei des verwendeten Themes hinzufügt.

   .. code::

      ....
      .oeVATTBEBasketItemInvalid {
      background-color: #e70404;
      }

|result|

In unserem Beispiel wird der Artikel im Warenkorb rot hervorgehoben (:ref:`oxdake01`).

.. _oxdake01:

.. figure:: /media/screenshots/oxdake01.png
   :scale: 100 %
   :alt: Nicht kaufbare Artikel im Warenkorb farblich hervorheben

   Abb.: Nicht kaufbare Artikel im Warenkorb farblich hervorheben











.. Intern: oxdake, Status:
