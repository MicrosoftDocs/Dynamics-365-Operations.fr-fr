---
title: Données principales client intégrées
description: Cette rubrique décrit l'intégration des données client entre Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a8030d9d1f1f3636a679d334afddad0f573a824e
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789186"
---
## <a name="integrated-customer-master"></a>Données principales client intégrées

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Il est courant que des enregistrements client soient gérés dans plusieurs applications. Par exemple, l'activité de vente peut entraîner des enregistrements client commerciaux via une application Microsoft Dynamics 365 for Sales, et les ventes de commerce électronique ou au détail entraîner des enregistrements client via une application Dynamics 365 for Finance and Operations. Indépendamment de l'origine de l'enregistrement client, il est intégré en arrière-plan, au delà des limites de l'application et des différences de l'infrastructure. Les données principales client intégrées permettent de traiter des scénarios de multi-gestion et de fournir une vue d'ensemble du client à la suite d'applications Dynamics 365.

## <a name="customer-data-flow"></a>Flux de données client

*Client* est un concept bien défini dans Finance and Operations et Common Data Service. Par conséquent, l'intégration des données client implique l'harmonisation du concept de client entre les applications Finance and Operations et Common Data Service. La relation des données est illustrée dans le flux de données client.

![Flux de données client](media/dual-write-customer-data-flow.png)

Les clients peuvent être classés largement en deux types : les clients commerciaux/organisationnels et les consommateurs/utilisateurs finaux. Ces deux types de clients sont stockés et gérés différemment dans Finance and Operations et Common Data Service.

Dans Finance and Operations, des clients commerciaux/organisationnels et des consommateurs/utilisateurs finaux sont gérés dans une table unique nommée **CustTable** (CustomerCustomerV3Entity), et ils sont classés selon l'attribut **Type**. (Si **Type** est défini sur **Organisation**, le client est commercial/organisationnel, et si **Type** est défini sur **Personne**, le client est client/utilisateur.) Les informations de principale personne à contacter sont traitées via l'entité de SMMContactPersonEntity.

Dans Common Data Service, les clients commerciaux/organisationnels sont gérés dans l'entité Compte et identifiés comme clients lorsque l'attribut **RelationshipType** est défini sur **Client**. Les consommateurs/utilisateurs finaux et la personne à contacter sont représentés par l'entité Contact. Pour fournir une séparation claire entre un consommateur/utilisateur final et une personne à contacter, l'entité **Contact** a un indicateur booléen nommé **Vendable**. Lorsque **Vendable** est **True**, le contact est un consommateur/utilisateur final, et des devis et des commandes peuvent être créés pour ce contact. Lorsque **Vendable** est **False**, le contact est simplement une principale personne à contacter d'un client.

Lorsqu'un contact non vendable participe à un processus de devis ou de commande, **Vendable** est défini sur **True** pour indiquer que le contact est un contact de vente. Un contact qui devient un contact de vente reste un contact de vente.

## <a name="templates"></a>Modèles

Les données client incluent toutes les informations sur le client, telles que le groupe de clients, les adresses, les informations de contact, le profil de paiement, le profil de facture, et le statut de fidélité. Un ensemble de mappages d'entités fonctionne ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.

Finance and Operations    | Application Customer Engagement
--------------------------|---------------------------------
Customer V3               | Compte
Customer V3               | Contact
Contacts CDS V2           | Contact
Groupes de clients           | Msdyn\_customergroups
Mode de paiement du client   | Msdyn\_customerpaymentmethods
Carte de fidélité              | Msdyn\_loyaltycards
Echéancier de paiement          | Msdyn\_paymentschedules
Echéancier de paiement          | Msdyn\_paymentschedulelines
Jour de paiement CDS           | Msdyn\_paymentdays
Lignes de jour de paiement CDS     | Msdyn\_paymentdaylines
Conditions de paiement          | Msdyn\_paymentterms
Affixes de nom              | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="customer-v3-to-account"></a>Customer V3 à Compte

Ce modèle synchronise les informations principales client pour les clients commerciaux et organisationnels entre Finance and Operations et Common Data Service.

<!-- ![](media/dual-write-account-1.png) -->

<!-- ![](media/dual-write-account-2.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
CUSTOMERACCOUNT | = | accountnumber
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
CREDITLIMIT | = | creditlimit
DELIVERYADDRESSCITY | = | address1\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
DELIVERYADDRESSCOUNTY | = | address1\_county
DELIVERYADDRESSLATITUDE | \> | address1\_latitude
DELIVERYADDRESSLONGITUDE | \> | address1\_longitude
DELIVERYADDRESSZIPCODE | = | address1\_postalcode
ORGANIZATIONNAME | = | name
ORGANIZATIONNUMBEROFEMPLOYEES | = | numberofemployees
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTTWITTER | = | primarytwitterid
PRIMARYCONTACTURL | = | websiteurl
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | description
CREDITLIMITISMANDATORY | \>\< | msdyn\_creditlimitismandatory
CREDITRATING | = | msdyn\_creditrating
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
INVOICEACCOUNT | = | msdyn\_billingaccount.accountnumber
INVOICEADDRESS | \>\< | msdyn\_invoiceaddress
ISONETIMECUSTOMER | \>\< | msdyn\_onetimecustomer
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PAYMENTDAY | = | msdyn\_paymentday.msdyn\_name
PAYMENTMETHOD | = | msdyn\_customerpaymentmethod.msdyn\_name
PAYMENTSCHEDULE | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTTERMS | = | msdyn\_paymentterm.msdyn\_name
PAYMENTTERMSBASEDAYS | = | msdyn\_paymenttermsbasedays
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
PRIMARYCONTACTLINKEDIN | = | msdyn\_primarylinkedinid
TAXEXEMPTNUMBER | = | msdyn\_taxexemptnumber
VENDORACCOUNT | = | msdyn\_vendor.msdyn\_vendoraccountnumber
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
LANGUAGEID | \<\< | aucun
DELIVERYADDRESSSTREET | = | address1\_line1
DELIVERYADDRESSSTATE | = | address1\_stateorprovince
aucun | \>\> | address1\_addresstypecode
aucun | \>\> | customertypecode
PARTYTYPE | \<\< | aucun
PARTYNUMBER | = | msdyn\_partynumber

## <a name="customer-v3-to-contact"></a>Customer V3 vers Contact

Ce modèle synchronise les données principales client pour consommateurs et utilisateurs finaux entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-contact-1.png) -->
<!-- ![](media/dual-write-contact-2.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
aucun | \>\> | msdyn\_sellable
PARTYTYPE | \<\< | aucun
PARTYNUMBER | = | msdyn\_partynumber
CUSTOMERACCOUNT | = | msdyn\_contactpersonid
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
PERSONFIRSTNAME | = | firstname
PERSONLASTNAME | = | lastname
PERSONMIDDLENAME | = | middlename
PERSONPROFESSIONALTITLE | = | jobtitle
PERSONGENDER | \>\< | gendercode
PERSONMARITALSTATUS | \>\< | familystatuscode
LANGUAGEID | \<\< | aucun
ADDRESSCITY | = | address1\_city
ADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
ADDRESSCOUNTY | = | address1\_county
ADDRESSLATITUDE | \> | address1\_latitude
ADDRESSLONGITUDE | \> | address1\_longitude
ADDRESSLOCATIONROLES | \<\< | aucun
ADDRESSSTATE | = | address1\_stateorprovince
ADDRESSSTREET | = | address1\_line1
ADDRESSZIPCODE | = | address1\_postalcode
ADDRESSPOSTBOX | = | address1\_postofficebox
aucun | \>\> | address1\_addresstypecode
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
aucun | \>\> | address2\_addresstypecode
DELIVERYADDRESSCITY | = | address3\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3\_country
DELIVERYADDRESSCOUNTY | = | address3\_county
DELIVERYADDRESSLATITUDE | \> | address3\_latitude
DELIVERYADDRESSLONGITUDE | \>\> | address3\_longitude
DELIVERYADDRESSSTATE | = | address3\_stateorprovince
DELIVERYADDRESSSTREET | = | address3\_line1
DELIVERYADDRESSZIPCODE | = | address3\_postalcode
aucun | \>\> | address3\_addresstypecode
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTLINKEDIN | = | msdyn\_primaryinkedinid
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTER | = | msdyn\_primarytwitterid
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURL | = | websiteurl
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | description

## <a name="contacts"></a>Contacts

Ce modèle synchronise toutes les informations de contact principales, secondaires et tertiaires, pour les clients et les fournisseurs, entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-contacts.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn\_partynumber
ASSOCIATEDCONTACTTYPE | \<\< | aucun
FIRSTNAME | = | firstname
MIDDLENAME | = | middlename
LASTNAME | = | lastname
ASSOCIATEDCONTACTNUMBER | = | msdyn\_vendorcontactid.msdyn\_vendoraccountnumber
PRIMARYADDRESSCITY | = | address1\_city
PRIMARYADDRESSCOUNTRYREGIONID | = | address1\_country
PRIMARYADDRESSCOUNTYID | = | address1\_county
PRIMARYFAXNUMBER | = | fax
PRIMARYADDRESSSTATEID | = | address1\_stateorprovince
PRIMARYADDRESSSTREET | = | address1\_line1
PRIMARYADDRESSZIPCODE | = | address1\_postalcode
PRIMARYPHONENUMBER | = | telephone1
PRIMARYEMAILADDRESS | = | emailaddress1
EMPLOYMENTDEPARTMENT | = | département
NOTES | = | description
GENDER | \>\< | gendercode
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid
PRIMARYURL | = | websiteurl
MARITALSTATUS | \>\< | familystatuscode
ISRECEIVINGDIRECTMAIL | \>\< | donotemail
EMPLOYMENTPROFESSION | = | jobtitle
SPOUSENAME | = | spousesname
aucun | \>\> | msdyn\_contactforvendor
aucun | \>\> | msdyn\_contactpersonid

## <a name="customer-groups"></a>Groupes de clients

Ce modèle synchronise les informations de groupe de clients entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-customer-groups.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
CUSTOMERGROUPID | = | msdyn\_groupid
DESCRIPTION | = | msdyn\_description
ISSALESTAXINCLUDEDINPRICE | \>\< | msdyn\_issalestaxincludedinprice
PAYMENTTERMID | = | msdyn\_paymenttermid.msdyn\_name
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymenttermname.msdyn\_name

## <a name="customer-payment-methods"></a>Modes de paiement des clients

Ce modèle synchronise les informations de mode de paiement des clients entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-customer-payment-methods.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | = | msdyn\_name
ACCOUNTTYPE | \>\< | msdyn\_accounttype
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingpostingenabled
ISSEPA | \>\< | msdyn\_issepa
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
DESCRIPTION | = | msdyn\_description
PAYMENTTYPE | \>\< | msdyn\_paymenttype
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | \>\< | msdyn\_invoiceupdate
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_enablepostdatescheckclearingposting
BILLOFEXCHANGEDRAFTTYPE | \>\< | msdyn\_billofexchangedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

## <a name="loyalty-cards"></a>Cartes de fidélité

Ce modèle synchronise les informations de carte de fidélité entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-loyalty-cards.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
CARDNUMBER | = | msdyn\_cardnumber
CARDTENDERTYPE | \>\< | msdyn\_cardtendertype
PARTYNUMBER | = | msdyn\_partynumber
REPLACEMENTCARDNUMBER | \> | msdyn\_replacementcardnumber
OMOPERATINGUNITNUMBER | = | msdyn\_operatingunitnumber
LOYALTYENROLLMENTDATE | = | msdyn\_enrollmentdate

## <a name="payment-schedules"></a>Echéanciers de paiement

Ce modèle synchronise les données de référence de l'échéancier de paiement pour les clients et les fournisseurs entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-payment-schedules.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | = | msdyn\_name
DESCRIPTION | = | msdyn\_description
ALLOCATIONMETHOD | \>\< | msdyn\_allocationmethod
PAYMENTFREQUENCYUNITS | \>\< | msdyn\_paymentfrequencyunit
PAYMENTFREQUENCY | = | msdyn\_paymentfrequency
NUMBEROFPAYMENTS | = | msdyn\_numberofpayments
FIXEDPAYMENTAMOUNT | = | msdyn\_fixedpaymentamount
MINIMUMPAYMENTAMOUNT | = | msdyn\_minimumpaymentamount
SALESTAXALLOCATIONMETHOD | \>\< | msdyn\_salestaxallocationmethod
NOTES | = | msdyn\_note

## <a name="payment-schedule-lines"></a>Lignes d'échéancier de paiement

Synchronise les données de référence des lignes d'échéancier de paiement pour les clients et les fournisseurs entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-payment-schedule-lines.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTSCHEDULENAME | \> | msdyn\_name
LINENUMBER | = | msdyn\_linenumber
PERIODSAFTERDUEDATE | = | msdyn\_periodsafterduedate
PERCENTORAMOUNT | \>\< | msdyn\_percentoramount
PERCENTORAMOUNTVALUE | = | msdyn\_percentoramountvalue

## <a name="payment-days"></a>Jours de paiement

Ce modèle synchronise les données de référence du nombre de jour de paiement pour les clients et les fournisseurs entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-payment-days.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | = | msdyn\_name
DESCRIPTION | = | msdyn\_description

## <a name="payment-day-lines"></a>Lignes de jour de paiement

Ce modèle synchronise les données de référence des lignes de jour de paiement pour les clients et les fournisseurs entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-payment-day-lines.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
CDSINTEGRATIONKEY | = | msdyn\_paymentdaylineid
FREQUENCY | \>\< | msdyn\_frequency
DAYOFWEEK | \>\< | msdyn\_dayofweek
DAYOFMONTH | = | msdyn\_dayofmonth
NOM | = | msdyn\_paymentday.msdyn\_name

## <a name="payment-terms"></a>Conditions de paiement

Ce modèle synchronise les référence de données des conditions de paiement pour les clients et les fournisseurs entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-payment-terms.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
DESCRIPTION | = | msdyn\_description
NOM | = | msdyn\_name
NUMBEROFMONTHS | = | msdyn\_numberofmonth
CUTOFFDAYOFMONTH | = | msdyn\_cutoffdayofmonth
ISCASHPAYMENT | \>\< | msdyn\_iscashpayment
NUMBEROFDAYS | = | msdyn\_days
ISCERTIFIEDCOMPANYCHECK | \>\< | msdyn\_iscertifiedcompanycheck
ISDEFAULTPAYMENTTERM | \>\< | msdyn\_isdefaultpaymentterm
CREDITCARDPAYMENTTYPE | \>\< | msdyn\_creditcardpaymenttype
CREDITCARDCREDITCHECKTYPE | \>\< | msdyn\_creditcardcreditchecktype
PAYMENTDAYNAME | = | msdyn\_paymentdayname.msdyn\_name
PAYMENTMETHODTYPE | \>\< | msdyn\_paymentmethodtype
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedulename.msdyn\_name

## <a name="name-affixes"></a>Affixes de nom

Ce modèle synchronise les données de référence des affixes de noms pour les clients et les fournisseurs entre Finance and Operations et Customer Engagement.

<!-- ![](media/dual-write-name-affixes.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
AFFIX | = | msdyn\_affix
TYPE | \>\< | msdyn\_affixtype
DESCRIPTION | = | msdyn\_description
