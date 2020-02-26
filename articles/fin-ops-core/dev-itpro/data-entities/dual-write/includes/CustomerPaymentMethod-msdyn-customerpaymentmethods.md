## <a name="customer-payment-method-to-msdyn_customerpaymentmethods"></a>Mode de paiement client vers msdyn_customerpaymentmethods

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
NAME | = | msdyn_name | 
ACCOUNTTYPE | >< | msdyn_accounttype | 
DISCOUNTGRACEPERIODDAYS | = | msdyn_discountgraceperioddays | 
BRIDGINGPOSTINGENABLED | >< | msdyn_bridgingpostingenabled | 
ISSEPA | >< | msdyn_issepa | 
LASTFILENUMBER | = | msdyn_lastfilenumber | 
LASTFILENUMBERTODAY | = | msdyn_lastfilenumbertoday | 
DESCRIPTION | = | msdyn_description | 
PAYMENTTYPE | >< | msdyn_paymenttype | 
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | >< | msdyn_invoiceupdate | 
PAYMENTSTATUS | >< | msdyn_paymentstatus | 
SUMBYPERIOD | >< | msdyn_sumbyperiod | 
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | >< | msdyn_enablepostdatescheckclearingposting | 
BILLOFEXCHANGEDRAFTTYPE | >< | msdyn_billofexchangedrafttype | 
DIRECTDEBIT | >< | msdyn_directdebit | 
