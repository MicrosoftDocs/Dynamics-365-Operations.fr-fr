## <a name="fiscal-calendar-period-to-msdyn_fiscalcalendarperiods"></a>Période du calendrier fiscal vers msdyn_fiscalcalendarperiods

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
COMMENTS | = | msdyn_comments | 
ENDDATE | = | msdyn_enddate | 
MONTH | >< | msdyn_month | 
CALENDAR | = | msdyn_fiscalcalendar.msdyn_calendar | 
QUARTER | >< | msdyn_quarter | 
SHORTNAME | = | msdyn_shortname | 
STARTDATE | = | msdyn_startdate | 
TYPE | >< | msdyn_fiscalperiodtype | 
PERIODNAME | = | msdyn_periodname | 
FISCALYEAR | = | msdyn_fiscalcalendaryear.msdyn_name | 
CALENDAR | = | msdyn_fiscalcalendaryear.msdyn_fiscalcalendarname | 
