## <a name="currencies-to-transactioncurrencies"></a>Devises vers transactioncurrencies

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Filtre source : ((CURRENCYCODE ! = "999"))

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
CURRENCYCODE | = | isocurrencycode | 
NAME | = | currencyname | 
SYMBOL | = | currencysymbol | 
none | >> | exchangerate | 1
