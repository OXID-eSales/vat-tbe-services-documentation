Note the following restrictions:

* The payment modules :productname:`PayPal Checkout`, :productname:`Amazon Pay`, and :productname:`Unzer Payment for OXID` are not yet available for version 7 of OXID eShop.

  .. todo: Zahlungsmodule ergänzen, soabald verfügbarbar für eShop 7: vorerst ausblenden
     The :productname:`PayPal Checkout`, :productname:`Amazon Pay`, and :productname:`Unzer Payment for OXID` payment modules are compatible with :productname:`OXID eShop eVAT`: Even with the quick purchase feature, your customer is taken to a checkout page where the customer confirms the order data including the VAT rate.

* The quick purchase feature of :productname:`PayPal` or :productname:`PayPal Plus` modules is not compatible with :productname:`OXID eShop eVAT`.

  Reason: For customers who are not registered, the final price for telecommunication, broadcasting, television and services provided electronically cannot be calculated and passed on to PayPal.

  If a payment module is not compatible with :productname:`OXID eShop eVAT`, your OXID eShop uses only the standard VAT determination functionality, and the VAT determined may be incorrect.