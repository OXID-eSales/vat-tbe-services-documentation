For what / Where not?
=====================

With the :productname:`OXID eShop eVAT` module, integrate the taxation of telecommunication, broadcasting, television and electronically provided services into your OXID eShop.

For this purpose :productname:`OXID eShop eVAT` determines the customer location using the :emphasis:`billing address` of the customer and calculates the respective VAT accordingly.

Legal basis
-----------

The module :productname:`OXID eShop eVAT` helps you to comply with the EU implementing regulation no. 1042/2013 regarding the country of supply of services.

This EU implementing regulation states that from January 1, 2015, merchants and service providers, when selling their electronically provided services, must pay the VAT of the EU country where the private customer ("consumer (non-taxable person)") belongs. Previously, it was the VAT of the country where the business is located.

For more information, see the European Commission's website under: `ec.europa.eu/taxation_customs/news/vat-updated-version-moss-report-has-just-been-published-2016-05-12_en <https://ec.europa.eu/taxation_customs/news/vat-updated-version-moss-report-has-just-been-published-2016-05-12_en>`_.

Technical implementation
------------------------

Items that you define as electronically delivered services in your OXID eShop are marked as such at the time of purchase.

:productname:`OXID eShop eVAT` determines the country of origin of the private customer (B2C) according to the billing address and calculates the respective VAT accordingly.

* An OXID eShop :emphasis:`without` the module :productname:`OXID eShop eVAT` always uses the VAT rate you set as default in the administration area under :menuselection:`Master Settings --> Core Settings --> Settings. --> VAT` as default.
* An OXID eShop :emphasis:`with` the module :productname:`OXID eShop eVAT` calculates the VAT for items that you have defined as electronic products or services in your OXID eShop with the VAT rate that corresponds to the determined location of the private customer.
  |br|
  For all other items, the VAT rate that is the default in the store is used.

All data on which the calculation is based is saved when the order is placed.

On request, you can use it to prove the location of a customer (see :ref:`operation:Displaying the customer location in an order`).

Your benefits
-------------

* Define items individually or by category as electronic products or services and assign VAT rates for the desired countries.
* Take advantage of

  * the logging of the customer's location when ordering electronic products or services
  * the logging of the VAT ID number as proof for taxable customers ("business (taxable person)").
    |br|
    For taxable customers, the invoice will show the net price without VAT.
* Extend :productname:`OXID eShop eVAT` with custom determination methods if required.

.. todo: #tbd V.3: "the logging of the VAT ID number including date and time as proof for taxable customers ("business (taxable person)").

How it works
------------

Information on value added tax from the customer's point of view
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the frontend, all items with which you offer electronically provided services are marked with two asterisks ** (:ref:`oxdaka01`, item 1).

This mark on the item price appears on the front end, in the category view, the item detail page, and in various other places.

.. _oxdaka01:

.. figure:: /media/screenshots/oxdaka01.png
   :class: with-shadow
   :width: 650
   :alt: Marking of electronically provided services: Example of an article detail view

   Fig.: Marking of electronically provided services


At the bottom right of each page of the frontend, the two asterisks :guilabel:`**` indicate a service provided electronically (:ref:`oxdaka01`, item 2).

A link (:ref:`oxdaka01`, item 2) calls up the page on which you, as the store operator, inform your customers in detail about payment and delivery of your goods.
|br|
You edit the content of this page in the administration area under :menuselection:`Customer Info --> CMS ages` (see :ref:`configuration:Adding customer information about VAT rates`).


The ordering process from the customer's point of view
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When your customer adds an item with which you offer electronically provided services to the shopping cart, then the two asterisks :guilabel:`**` are displayed with the VAT (:ref:`oxdaka02`, item 1).

A message tells your customer which country the displayed VAT is based on and that the VAT may change once the customer is logged into the store (:ref:`oxdaka02`, item 2).

.. _oxdaka02:

.. figure:: /media/screenshots/oxdaka02.png
   :class: with-shadow
   :width: 650
   :alt: Order step 1 with reference to VAT calculation

   Fig.: Order step 1 with reference to VAT calculation


The VAT is calculated after registration or after specifying the billing address, after :productname:`OXID eShop eVAT` has determined the customer location (see :ref:`configuration:Configuring the customer location determination`).

A message tells the customer again which country is the basis for the VAT calculation (:ref:`oxdaka03`, items 1, 2).

Each time the country is changed, the VAT is recalculated and the message is updated.


.. _oxdaka03:

.. figure:: /media/screenshots/oxdaka03.png
   :class: with-shadow
   :width: 650
   :alt: Order step 1 with reference to customer location and VAT calculation

   Fig.: Order step 1 with reference to customer location and VAT calculation

What happens in case of error
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If a user comes from an EU country that you have not configured to calculate the VAT for electronic services, an error message appears.

The customer is asked to remove the item from the shopping cart (:ref:`oxdaka04`, item 1).

Reason: The VAT cannot be determined (:ref:`oxdaka04`, pos. 2).

To avoid the error case, follow the instructions under

* :ref:`configuration:Marking items as electronic products and assigning VAT rates`
* :ref:`configuration:Marking a category as electronic products and assigning VAT rates`


See also :ref:`extension:Highlighting non-purchasable items in a shopping cart`.

.. _oxdaka04:

.. figure:: /media/screenshots/oxdaka04.png
   :class: with-shadow
   :width: 650
   :alt: Determination of value added tax failed

   Fig.: Determination of value added tax failed


Compatibility
-------------

Payment modules
^^^^^^^^^^^^^^^

Do the following:

* Check if your payment modules are available for OXID eShop version 7.
* Ensure that your third-party payment modules are compatible with :productname:`OXID eShop eVAT`.

  For more information, see :ref:`configuration:Ensuring compatibility with payment modules`.

PDF Invoice
^^^^^^^^^^^

:productname:`PDFInvoice` (`pdf-invoice-module <https://github.com/OXIDprojects/pdf-invoice-module>`_) is not compatible with :productname:`OXID eShop eVAT` V. 3.0 for OXID eShop version 7 and above.





.. Intern: oxdaka, Status: