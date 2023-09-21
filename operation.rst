Operation
=========

Use the following functions of the :productname:`OXID eShop eVAT` module during operation:

* Displaying the customer location in the order
* Displaying the sales tax identification number


Displaying the customer location in an order
--------------------------------------------

If required, verify that :productname:`OXID eShop eVAT` has determined the customer location.

|prerequisites|

Your customer has purchased at least one item that qualifies as telecommunications, broadcasting, television, and electronically delivered service.

|procedure|

1. Choose :guilabel:`Administer Orders --> Orders`.
2. Choose an order that contains an electronic item.

|result|

On the :guilabel:`Main` tab, below the input area, the result of determining the customer location is displayed (:ref:`oxdakd01`, item 1).

.. _oxdakd01:

.. figure:: /media/screenshots/oxdakd01.png
   :class: with-shadow
   :width: 650
   :alt: Displaying the customer location in an order

   Figure: Displaying the customer location in an order


Displaying the VAT ID
---------------------

If required, display the customer's VAT ID and the date and time it was saved.

The :productname:`OXID eShop eVAT` module ensures that the VAT number (VAT ID) entered by a customer is saved along with the date and time when it is valid.

VAT ID, date and time give you an indication that and from when the customer is considered to be liable to pay VAT to the store.

Customers can provide the VAT ID when registering or during the ordering process. They can also enter it later in their customer accounts.

|procedure|

1. Choose :menuselection:`Administer Users --> Users`.
#. Choose the user.
#. Choose the :guilabel:`Main` tab.

|result|

The VAT ID is displayed (:ref:`oxdakd02`, item 1).

.. todo: #tbd 3.0: "with the date and time it was entered"

.. _oxdakd02:

.. figure:: /media/screenshots/oxdakd02.png
   :width: 450
   :alt: Displaying VAT ID

   Fig.: Displaying VAT ID


Maintaining VAT rates
---------------------

The current VAT rates of the different countries are statically stored in the module. They are not updated automatically.

Once you have enabled :productname:`OXID eShop eVAT`, as a store owner you need to maintain the VAT rates.

.. tip::

   To keep up to date with possible changes in VAT rates, subscribe to an information service.

|prerequisites|

When configuring :productname:`OXID eShop eVAT`, under :menuselection:`Administer Products --> Products --> <electronically supplied service> --> eVAT Settings` you have ensured that each item in question is assigned the VAT rate valid for that country.

For more information, see

* :ref:`configuration:Marking items as electronic products and assigning VAT rates`
* :ref:`configuration:Marking a category as electronic products and assigning VAT rates`

|procedure|

Maintain the VAT rates under :menuselection:`Master Settings --> Countries --> <country> --> VAT rates`.

For more information, see :ref:`configuration:Activating and maintaining country-specific VAT rates`



.. Intern: oxdakd, Status:

