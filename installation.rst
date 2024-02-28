Installation
============

Install the module :productname:`OXID eShop eVAT` for OXID eShop version 7.


|prerequisites|

* You have installed OXID eShop 7.
* You have PHP 8.0 or higher.


|procedure|


1. Open a shell and change to the root directory of the eShop (where the :file:`composer.json` file is located).
   |br|
   Example:

   .. code:: bash

      cd /var/www/oxideshop

#. To install the latest released version, run the following command:

   .. code:: bash

      composer require oxid-esales/evat-module:^3.0

   Alternatively, to install the latest unreleased version from Github, run the following command:

   .. code:: bash

      composer require oxid-esales/evat-module:dev-b-7.0.x

#. Confirm the queries.
#. Optional: Delete all files and folders except :file:`.htaccess` from the :file:`/tmp` directory of the store.


|result|


Once the installation process is complete, the :productname:`OXID eShop eVAT` module will appear in the administration area under :menuselection:`Extensions --> Modules` (:ref:`oxdakc01`).

.. _oxdakc01:

.. figure:: /media/screenshots/oxdakc01.png
   :width: 450
   :alt: Module eVAT installed

   Fig.: Module eVAT installed


Next step: To configure :productname:`OXID eShop eVAT`, choose :guilabel:`Next`.





.. Intern: oxdakc, Status: