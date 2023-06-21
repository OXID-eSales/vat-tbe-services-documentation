Module extension
================

Extend the :productname:`OXID eShop eVAT` module as needed.

We describe as an example,

* how to add a custom determination method for customer location
* how to highlight an item in the shopping cart whose VAT rate could not be determined.

Adding a method to determine the customer location
--------------------------------------------------

To add a custom method to determine the customer location, create a class and register it. In this way, you extend :productname:`OXID eShop eVAT` with your custom module.

.. note::

   The :technicalname:`GeoLocationEvidence` class is currently only prepared and needs to be implemented.

   This can be done by extending this class with a module and implementing the :technicalname:`GeoLocationEvidence::getCountryId()` method.


|procedure|

Do the following:

* For the new class to have an interface, make sure it extends the :technicalname:`Evidence` class.
* Register the class with :technicalname:`EvidenceRegister::registerEvidence()`.
* When the class is no longer needed, unregister the class with :technicalname:`EvidenceRegister::unregisterEvidence()`.
* Create a module that contains the new class.
* Enter the class in the :technicalname:`metadata.php` file of the module.
* For registering and unregistering the class, use the :technicalname:`onActivate()` and :technicalname:`onDeactivate()` events of the module.

  .. code::

     public static function onActivate()
        {
            if (class_exists('EvidenceRegister')) {
                $oConfig = Registry::getConfig();
                /** @var EvidenceRegister $oEvidenceRegister */
                $oEvidenceRegister = oxNew('EvidenceRegister', $oConfig);
                $oEvidenceRegister->registerEvidence('ExtendedEvidence1');
                $oEvidenceRegister->registerEvidence('ExtendedEvidence2');
            }
        }

        public static function onDeactivate()
        {
            if (class_exists('EvidenceRegister')) {
                $oConfig = Registry::getConfig();
                /** @var EvidenceRegister $oEvidenceRegister */
                $oEvidenceRegister = oxNew('EvidenceRegister', $oConfig);
                $oEvidenceRegister->unregisterEvidence('ExtendedEvidence1');
                $oEvidenceRegister->unregisterEvidence('ExtendedEvidence2');
            }
        }

  If the module did not unregister the new class when it was deactivated, the added determination methods will be removed the next time the customer location is determined.

* Activate your module with the additional determination methods only if the :productname:`OXID eShop eVAT` module is active.

  Otherwise :technicalname:`EvidenceRegister` will not be found.


Highlighting non-purchasable items in a shopping cart
-----------------------------------------------------

You want to highlight non-purchasable items in the shopping cart.

You can do this using a CSS class that you integrate into the :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl` template.

The information whether an item in the shopping cart is purchasable is provided by the controller method :technicalname:`isArticleValid`.

|background|

In some cases, an item may not be purchasable because its VAT cannot be calculated.

An example is the purchase of an item which is considered to be telecommunications, radio, television and services provided by electronic means.

If the VAT rates are missing for the country from which the customer wants to order, an error message is displayed with a reference to the item in question (see :ref:`intro:What happens in case of error`).

The customer has to remove the item from the shopping cart.

Color highlighting makes it easier for your customer to identify the item in question.

|procedure|

1. Create an extension module with a CCS class (in our example :code:`BasketItemInvalid`) and extend the template :technicalname:`/tpl/page/checkout/inc/basketcontents.tpl`:

   .. code::

      [{foreach key=basketindex from=$oxcmp_basket->getContents() item=basketitem name=basketContents}]
            [{block name="checkout_basketcontents_basketitem"}]
             ....
            <tr class="basketItem
             [{if !$oView->isArticleValid()}] BasketItemInvalid[{/if}]"
             id="cartItem_[{$smarty.foreach.basketContents.iteration}]">

2. Add the CSS class to the CSS file :technicalname:`/oe/oevattbe/out/src/css/vattbe.css` or to the CSS file of the theme you use.

   .. code::

      ....
      .oeVATTBEBasketItemInvalid {
      background-color: #e70404;
      }

|result|

In our example, the item name in the shopping cart is highlighted in red (:ref:`oxdake01`, item 1).

.. _oxdake01:

.. figure:: /media/screenshots/oxdake01.png
   :class: with-shadow
   :width: 650
   :alt: Highlighting non-purchasable items in the shopping cart by color

   Figure: Highlighting non-purchasable items in the shopping cart in color


.. Intern: oxdake, Status:
