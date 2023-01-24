Modul-Erweiterung
=================

Erweitern Sie das Modul :productname:`OXID eShop eVAT` bei Bedarf.

Wir beschreiben beispielhaft,

* wie Sie eine eigene Bestimmungsmethode für den Kundenstandort hinzufügen
* wie Sie einen Artikel im Warenkorb farblich hervorheben können, dessen Mehrwertsteuersatz nicht ermittelt werden konnte.

Bestimmungsmethode für Kundenstandort hinzufügen
------------------------------------------------

Um eine eigene Bestimmungsmethode für den Kundenstandort hinzuzufügen, erstellen Sie eine Klasse und registrieren sie. Sie erweitern :productname:`OXID eShop eVAT` also mit einem eigenen Modul.

.. note::

   Die Klasse :technicalname:`oeVATTBEGeoLocationEvidence` ist derzeit nur vorbereitet und muss implementiert werden.

   Das kann durch Erweitern dieser Klasse mit einem Modul und Implementierung der Methode :technicalname:`oeVATTBEGeoLocationEvidence::getCountryId()` umgesetzt werden.


|procedure|

Tun Sie Folgendes:

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

* Aktivieren Sie Ihr Modul mit den zusätzlichen Bestimmungsmethoden nur dann, wenn das Modul :productname:`OXID eShop eVAT` aktiv ist.

  Andernfalls wird :technicalname:`oeVATTBEEvidenceRegister` nicht gefunden.


Nicht kaufbare Artikel im Warenkorb hervorheben
-----------------------------------------------

Sie wollen nicht kaufbare Artikel im Warenkorb farblich hervorheben.

Das setzen Sie mit Hilfe einer CSS-Klasse um, die Sie in das Template :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl` integrieren.

Die Information, ob ein Artikel im Warenkorb kaufbar ist, liefert Ihnen die Controller-Methode :technicalname:`isOeVATTBETBEArticleValid`.

|background|

In einigen Fällen kann es sein, dass ein Artikel nicht gekauft werden kann, weil sich seine Mehrwertsteuer nicht berechnen lässt.

Ein Beispiel ist der Kauf eines Artikels, welcher als Telekommunikations-, Rundfunk-, Fernseh- und auf elektronischem Weg erbrachte Dienstleistungen gilt.

Fehlen die Mehrwertsteuersätze bei dem Land, aus dem der Kunde bestellen möchte, wird eine Fehlermeldung mit Hinweis auf den betreffenden Artikel angezeigt (siehe :ref:`intro:Was im Fehlerfall passiert`).

Der Kunde muss den Artikel aus dem Warenkorb entfernen.

Durch eine farbliche Hervorhebung kann Ihr Kunde den betreffenden Artikel leichter identifizieren.

|procedure|

1. Erstellen Sie ein Erweiterungsmodul mit einer CCS-Klasse (in unserem Beispiel :code:`oeVATTBEBasketItemInvalid`) und erweitern Sie das Template :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl`:

   .. code::

      [{foreach key=basketindex from=$oxcmp_basket->getContents() item=basketitem name=basketContents}]
            [{block name="checkout_basketcontents_basketitem"}]
             ....
            <tr class="basketItem
             [{if !$oView->isOeVATTBETBEArticleValid()}] oeVATTBEBasketItemInvalid[{/if}]"
             id="cartItem_[{$smarty.foreach.basketContents.iteration}]">

2. Fügen Sie die CSS-Klasse der CSS-Datei :technicalname:`/oe/oevattbe/out/src/css/vattbe.css` oder der CSS-Datei des verwendeten Themes hinzu.

   .. code::

      ....
      .oeVATTBEBasketItemInvalid {
      background-color: #e70404;
      }

|result|

In unserem Beispiel ist die Artikelbezeichnung im Warenkorb rot hervorgehoben (:ref:`oxdake01`, Pos. 1).

.. _oxdake01:

.. figure:: /media/screenshots/oxdake01.png
   :class: with-shadow
   :width: 650
   :alt: Nicht kaufbare Artikel im Warenkorb farblich hervorheben

   Abb.: Nicht kaufbare Artikel im Warenkorb farblich hervorheben


.. Intern: oxdake, Status:
