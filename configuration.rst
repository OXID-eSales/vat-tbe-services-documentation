Configuration
=============

Make the :productname:`OXID eShop eVAT` module operational for your OXID eShop.

Basic procedure
------------------------

1. Activate the module.
#. Assign VAT rates to countries and activate countries for the specific VAT calculation.
#. Mark items or categories of items as electronic products or services.
#. Set the methods for determining the customer location.
#. Verify the store location.
#. Ensure compatibility with payment modules.

Activating eVAT
---------------

Enable :productname:`OXID eShop eVAT` in each subshop where you want to use the module.

|procedure|

1. Choose :menuselection:`Extensions --> Modules`.
2. Choose the module :guilabel:`eVAT` and choose :menuselection:`Overview --> Activate`.

Configuring eVAT
----------------

Activating and maintaining country-specific VAT rates
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Activate the calculation of the VAT for the relevant countries.

Check the statically stored VAT rates and adjust them if necessary.

.. attention::
   **Maintaining VAT rates as store owner**

   VAT rates are already prepared for the countries of the European Union.

   VAT rates are statically stored in the module, they are not automatically adjusted.

   When you activate the module, it will check if there is already an entry for the country:

   * If yes, nothing is done.
   * If no, the value is taken from the list.

   If the module is activated, you as a store owner have to maintain the VAT rates.

   For more information, see :ref:`operation:Maintaining VAT rates`.


.. note::
   **OXID eShop Enterprise Edition**

   In case of an Enterprise Edition, adjustments of the VAT rates affect all subhops/clients.

|procedure|

1. Choose :menuselection:`Master Settings --> Countries`.
#. Choose the country to which you want to apply the EU directive and choose the :guilabel:`Main` tab.
#. Activate the :guilabel:`Apply VAT module` checkbox (:ref:`oxdakb01a`).

   .. _oxdakb01a:

   .. figure:: /media/screenshots/oxdakb01a.png
      :class: with-shadow
      :width: 650
      :alt: Applying the eVAT module VAT

      Fig.: Applying the eVAT module VAT

#. To adjust the stored VAT rates, if necessary, or to create new VAT rates, choose the :guilabel:`Country VAT rates` (:ref:`oxdakb01`, pos. 1) tab.
   |br|
   The VAT rates for the European Union countries are already prepared.
   |br|
   If needed: Adjust them to the current regulations or delete them.
   |br|
   If needed: Create new VAT rates under :guilabel:`Create new VAT rate`, each with a name, a percentage and an optional description.
   |br|
   Example: For the United Kingdom, add the zero rate applicable in 2022 for, among other things, printed books and newspapers and audio books for the blind (:ref:`oxdakb01`, item 2).

   .. _oxdakb01:

   .. figure:: /media/screenshots/oxdakb01.png
      :class: with-shadow
      :width: 650
      :alt: Adjusting VAT rates, example United Kingdom

      Fig.: Adjusting VAT rates, example United Kingdom

#. Save your settings.

Marking items as electronic products and assigning VAT rates
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Make items that belong to telecommunication, broadcasting, television and services provided electronically identifiable as such.

Alternatively: Mark all items in a category as electronic products or services (see :ref:`configuration:Marking a category as electronic products and assigning VAT rates`).

.. note::
   **OXID eShop Enterprise Edition**

   With an Enterprise Edition you can only customize the items of the parent store. The property of an electronic product or service is inherited to the subshops.

   Items or categories that you create in a subshop can be marked as electronic services separately.

|procedure|

1. Under :menuselection:`Administer Products --> Products`, choose the product.
#. Choose :guilabel:`eVAT Settings` tab.
#. Choose the :guilabel:`Product is a telecommunication, broadcasting or electronic service` checkbox (:ref:`oxdakb02`, item 1).
#. Assign the applicable VAT rates for each country to the item.
   |br|
   For example, an eBook has the standard rate in the UK, and the reduced rate 1 in France (:ref:`oxdakb02`, item 2).

   .. attention::

      **Conversion at risk**.

      If the VAT rate assignment for a country is missing, the customer must remove the item in question from the shopping cart.

      In our example (:ref:`intro:What happens in case of error`) a customer from Austria cannot buy the eBook and receives a corresponding message.

.. _oxdakb02:

.. figure:: /media/screenshots/oxdakb02.png
   :class: with-shadow
   :width: 650
   :alt: Assigning VAT rates to an item

   Fig.: Assigning VAT rates to an item


Marking a category as electronic products and assigning VAT rates
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Mark all items in a category as electronic products or services.

.. important::
   **Overwriting item-specific eVAT settings**

   Changes to eVAT settings will overwrite all individual eVAT settings on all items in that category.


|procedure|

1. Choose :menuselection:`Administer Products --> Categories`.
#. Choose the product category.
#. Choose the :guilabel:`eVAT Settings` tab.
#. Choose the :guilabel:`Products in this category are electronic services` checkbox (:ref:`oxdakb03`, item 1).
#. Assign the valid VAT rates for each country to the item (:ref:`oxdakb03`, item 2).

   .. attention::

      **Conversion at risk**.

      If the VAT rate assignment for a country is missing, the customer must remove the item in question from the shopping cart.

      In our example (:ref:`intro:What happens in case of error`), a customer from Austria cannot buy the eBook and receives a corresponding message.

#. Save your settings.

.. _oxdakb03:

.. figure:: /media/screenshots/oxdakb03.png
   :class: with-shadow
   :width: 650
   :alt: Defining items of a category as electronic services

   Fig.: Defining items of a category as electronic services

Configuring the customer location determination
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Enable determining the customer location.


|background|

The Implementing Regulation (EU) No 1042/2013 requires that the country of origin of the customer ordering a telecommunications, broadcasting, television and electronically supplied service must be determined in order to correctly calculate VAT.

The customer's location must be determined by at least two checks. Simply indicating the customer in the ordering process is not sufficient; you must verify the customer's information.

The :productname:`OXID eShop eVAT` module uses the customer's billing address to determine the customer location.

You can add custom determination methods if needed (see :ref:`extension:Adding a method to determine the customer location`).

|Procedure|

1. Choose :menuselection:`Extensions --> Modules`.
#. Choose the :guilabel:`OXID eShop eVAT` module and choose the :guilabel:`Settings` tab.
#. Under :guilabel:`eVAT customer location method`, make sure that the :guilabel:`Determine customer location using billing address` determination method is enabled.
   |br|
   To do this, do the following:

   a. Make sure that the :technicalname:`billing_country` parameter is assigned the :technicalname:`1` value (:ref:`oxdakb04`, item 1).

   .. code::

      billing_country => 1

   b. Make sure :code:`billing_country` is selected as the default determination method (:ref:`oxdakb04`, item 2).

   .. _oxdakb04:

   .. figure:: /media/screenshots/oxdakb04.png
      :class: with-shadow
      :width: 650
      :alt: Configuring the determination method

      Fig.: Configuring the  determination method

   .. note::

      The :code:`geo_location` determination method is not implemented.

#. Save your settings.


|result|

The result of the check will be saved in the order.

In the current operation, you can check the result of determining the customer location in the order (see :ref:`operation:Displaying the customer location in an order`).


Verifying the store location
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Make sure that the store location is configured correctly.

.. todo: #tb:: add as of V.3
    |background|
    The system checks if a customer is from the same country where the store is located.
    If this is the case, the VAT rate defined as default for the store will be used to calculate the value of goods.
    If you enter an invalid country code, the store behaves as if no country is entered.
    Items representing telecommunication, radio, television and electronically provided services will not be marked as such.
    No related messages will be displayed.

|procedure|

1. Choose :menuselection:`Extensions --> Modules`.
#. Choose the :guilabel:`OXID eShop eVAT` module and choose the :guilabel:`Settings` tab.
#. In the :guilabel:`Place of Business` field, enter the country code for the store location in ISO2 format (in our example :code:`de` for Germany: :ref:`oxdakb04`, item 3).

Adding customer information about VAT rates
-------------------------------------------

Inform your customers about the different VAT rates.

Your customers can access this information via a link on the item detail page (see :ref:`intro:Information on value added tax from the customer's point of view`, item 2).

|procedure|

1. In the administration area, choose :menuselection:`Customer Info --> CMS pages`.
#. Call the page with the ID :technicalname:`oxdeliveryinfo`.
#. Add information related to special items and new VAT calculation (:ref:`oxdakb05a`).
#. Save your settings.


.. _oxdakb05a:

.. figure:: /media/screenshots/oxdakb05a.png
   :class: with-shadow
   :width: 650
   :alt: Adding customer information about value added tax

   Fig.: Adding customer information about value added tax


Ensuring compatibility with payment modules
-------------------------------------------

If you use third-party payment modules, make sure that your payment modules are compatible with :productname:`OXID eShop eVAT`.

Experience has shown that there may be problems with the Quick Purchase function (express checkout).

Therefore, check if the Quick Purchase function of your payment module works with :productname:`OXID eShop eVAT`. If it does not work, turn it off and check again.

|background|

For customers who are not registered, the final price for telecommunication, broadcasting, television and services provided electronically cannot be calculated and passed on to PayPal.
|br|
If a payment module is not compatible with :productname:`OXID eShop eVAT`, your OXID eShop uses only the standard VAT determination functionality, and the VAT determined may be incorrect.

.. todo: Folgendes ergänzen, sobald Zahlungsmodule für eShop 7 verfügbar
    You do :emphasis:`not` need to do anything if you
    * use a payment module without a quick purchase feature, for example :productname:`Unzer Payment for OXID`
    * use the :productname:`OXID eShop eVAT`-compatible payment modules :productname:`PayPal Checkout` or :productname:`Amazon Pay`.


|procedure|

1. Check if your payment module works correctly.
   |br|
   In particular, check whether the Quick Purchase function works.
#. If it does not work, disable the Quick Purchase function of your payment module:

   a. Navigate to the third-party payment module settings.
   #. Make sure only the default payment method is enabled.
   #. Disable functions related to "quick purchase" or "express checkout" or similar.

      For more information, see your payment module documentation.

   #. Save your settings.

#. Test whether the payment module works with the Quick Purchase function disabled.

   Expected result: the Quick Purchase function is disabled, orders are not completed immediately by the payment provider, but the customer lands on the checkout page and the customer has to confirm the order with the correctly determined VAT.

#. If your payment module does not work even with the Quick Purchase function disabled or if it does not allow to disable the Quick Purchase function, disable the payment module for the electronic items.

.. Intern: oxdakb, Status: