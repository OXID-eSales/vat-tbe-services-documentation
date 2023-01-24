Installation
============

Install the module :productname:`OXID eShop eVAT` for OXID eShop version 6.0 and higher.


|prerequisites|

* You have installed OXID eShop 6.0 or higher.
* You have PHP 5.6 or higher.


|procedure|


1. Open a shell and change to the root directory of the eShop (where the :file:`composer.json` file is located).
   |br|
   Example:

   .. code:: bash

      cd /var/www/oxideshop

#. To install the latest released version, run the following command:

   .. code:: bash

      composer require oxid-esales/evat-module:^2.0

   Alternatively, to install the latest unreleased version from Github, run the following command:

   .. code:: bash

      composer require oxid-esales/evat-module:dev-master

#. Confirm the queries.
#. Optional: Delete all files and folders except :file:`.htaccess` from the :file:`/tmp` directory of the store.

.. todo: #HR:  composer require oxid-esales/evat-module:^2.0 führt zu  "Metadata version 1.2 is not supported"

|result|


Once the installation process is complete, the :productname:`OXID eShop eVAT` module will appear in the administration area under :menuselection:`Extensions --> Modules` (:ref:`oxdakc01`).

.. todo: #tbd:  oxdakc01 EN einfügen

.. _oxdakc01:

.. figure:: /media/screenshots/oxdakc01.png
   :scale: 100 %
   :alt: Module eVAT installed

   Fig.: Module eVAT installed


Next step: To configure :productname:`OXID eShop eVAT`, choose :guilabel:`Next`.





.. Intern: oxdakc, Status: