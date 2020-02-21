## <a name="terms-of-payment-to-msdyn_paymentterms"></a>Conditions de paiement vers msdyn_paymentterms

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
DESCRIPTION | = | msdyn_description | 
NAME | = | msdyn_name | 
NUMBEROFMONTHS | = | msdyn_numberofmonth | 
CUTOFFDAYOFMONTH | = | msdyn_cutoffdayofmonth | 
ISCASHPAYMENT | >< | msdyn_iscashpayment | 
NUMBEROFDAYS | = | msdyn_days | 
ISCERTIFIEDCOMPANYCHECK | >< | msdyn_iscertifiedcompanycheck | 
ISDEFAULTPAYMENTTERM | >< | msdyn_isdefaultpaymentterm | 
CREDITCARDPAYMENTTYPE | >< | msdyn_creditcardpaymenttype | 
CREDITCARDCREDITCHECKTYPE | >< | msdyn_creditcardcreditchecktype | 
PAYMENTDAYNAME | = | msdyn_paymentdayname.msdyn_name | 
PAYMENTMETHODTYPE | >< | msdyn_paymentmethodtype | 
PAYMENTSCHEDULENAME | = | msdyn_paymentschedulename.msdyn_name | 
