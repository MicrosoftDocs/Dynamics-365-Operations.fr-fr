## <a name="fiscal-calendar-year-integration-entity-to-msdyn_fiscalcalendaryears"></a>Entité Intégration de l'exercice du calendrier fiscal vers msdyn_fiscalcalendaryears

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
FISCALCALENDAR_CALENDARID | = | msdyn_fiscalcalendarname | 
NAME | = | msdyn_name | 
STARTDATE | = | msdyn_startdate | 
ENDDATE | = | msdyn_enddate | 
FISCALCALENDAR_CALENDARID | = | msdyn_calendar.msdyn_calendar | 
