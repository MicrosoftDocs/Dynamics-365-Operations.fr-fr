## <a name="ledger-to-msdyn_ledgers"></a>Comptabilité vers msdyn_ledgers

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
LEGALENTITYID | >> | msdyn_company.cdm_companycode | 
DESCRIPTION | >> | msdyn_description | 
ACCOUNTINGCURRENCY | >> | msdyn_accountingcurrency.isocurrencycode | 
ISBUDGETCONTROLENABLED | >> | msdyn_isbudgetcontrolenabled | 
NAME | >> | msdyn_name | 
REPORTINGCURRENCY | >> | msdyn_reportingcurrency.isocurrencycode | 
BUDGETEXCHANGERATETYPE | >> | msdyn_budgetexchangeratetype.msdyn_name | 
CHARTOFACCOUNTS | >> | msdyn_chartofaccounts.msdyn_name | 
EXCHANGERATETYPE | >> | msdyn_exchangeratetype.msdyn_name | 
FISCALCALENDAR | >> | msdyn_fiscalcalendar.msdyn_calendar | 
REPORTINGCURRENCYEXCHANGERATETYPE | >> | msdyn_reportingcurrencyexchangeratetype.msdyn_name | 
