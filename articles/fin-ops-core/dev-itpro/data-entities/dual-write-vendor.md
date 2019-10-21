---
title: Données principales fournisseur intégrées
description: Cette rubrique décrit l'intégration des données fournisseur entre les applications Finance and Operations et Common Data Service.
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
ms.openlocfilehash: 2b8d1e872b65f40a63c0771cb95d8d1c0875ca82
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249084"
---
## <a name="integrated-vendor-master"></a>Données principales fournisseur intégrées

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Le terme *fournisseur* fait référence à une organisation de fournisseur ou un propriétaire unique qui fait partie du processus de la chaîne d'approvisionnement, et qui fournit des marchandises pour l'entreprise. Bien que *fournisseur* est un concept établi dans les applications Finance and Operations, il n'existe pas de concept de fournisseur dans d'autres applications Dynamics 365. Au lieu de cela, certaines entreprises surchargent l'entité Compte pour enregistrer les informations client et fournisseur. D'autres sociétés utilisent un concept de fournisseur personnalisé. L'intégration de Common Data Service prend en charge ces deux conceptions. Par conséquent, vous pouvez activer l'une des conceptions, selon le scénario de l'entreprise.

L'intégration des données fournisseur entre les applications Finance and Operations et d'autres applications Dynamics 365 de multi-gérer les données. Indépendamment de l'origine des données fournisseur, elles sont intégrés en arrière-plan, au delà des limites de l'application et des différences de l'infrastructure. 

### <a name="vendor-data-flow"></a>Flux de données fournisseur

Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et si vous souhaitez isoler les informations fournisseur des informations client, vous pouvez utiliser la nouvelle conception de fournisseur.

![Flux de données fournisseur](media/dual-write-vendor-data-flow.png)

Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et que vous souhaitez continuer d'utiliser l'entité Compte pour stocker les informations fournisseur, vous pouvez utiliser la nouvelle conception de fournisseur étendue. Dans cette conception, les informations fournisseur étendues, telles que le groupe de fournisseurs et le profil de validation fournisseur, sont enregistrées dans les détails du fournisseur.

![Flux de données fournisseur étendues](media/dual-write-vendor-detail.jpg)

Les informations de contact fournisseur ressemblent aux informations de contact client. En arrière-plan, les informations de la personne à contacter sont stockées et extraites des mêmes entités.

## <a name="templates"></a>Modèles

Les données fournisseur incluent toutes les informations sur le fournisseur, telles que le groupe de fournisseurs, les adresses, les informations de contact, le profil de paiement et le profil de facture. Un ensemble de mappages d'entités fonctionne ensemble pendant l'interaction des données fournisseur, comme indiqué dans le tableau suivant.

Applications Finance and Operations  | Autres applications Dynamics 365
------------------------|---------------------------------
Vendor V2               | Compte
Vendor V2               | Msdyn\_vendors
Contacts CDS V2         | Contact
Groupes de fournisseurs           | Msdyn\_vendorgroups
Mode de paiement fournisseur   | Msdyn\_vendorpaymentmethods
Echéancier de paiement        | Msdyn\_paymentschedules
Echéancier de paiement        | Msdyn\_paymentschedulelines
Jour de paiement CDS         | Msdyn\_paymentdays
Lignes de jour de paiement CDS   | Msdyn\_paymentdaylines
Conditions de paiement        | Msdyn\_paymentterms
Affixes de nom            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Vendor V2 et Compte 

Les sociétés qui utilisent l'entité Compte pour stocker les informations fournisseur peuvent continuer de l'utiliser de la même manière. Elles peuvent également bénéficier de la prochaine fonctionnalité de fournisseur explicite en raison de l'intégration des applications Finance and Operations.

## <a name="vendor-v2-and-msdyn_vendors"></a>Vendor V2 et Msdyn\_vendors

Les sociétés qui utilisent une solution personnalisée pour les fournisseurs peuvent profiter du concept de fournisseur prédéfini introduit dans Common Data Service en raison de l'intégration des applications Finance and Operations. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
VENDORACCOUNTNUMBER | = | msdyn\_vendoraccountnumber
VENDORGROUPID | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
VENDORORGANIZATIONNAME | = | msdyn\_name
VENDORPARTYTYPE | \>\< | msdyn\_isperson
PERSONFIRSTNAME | = | msdyn\_firstname
PERSONLASTNAME | = | msdyn\_lastname
CREDITLIMIT | = | msdyn\_vendorcreditlimit
ISFOREIGNENTITY | \>\< | msdyn\_isforeignentity
ISONETIMEVENDOR | \>\< | msdyn\_isonetimevendor
ADDRESSBUILDINGCOMPLIMENT | = | msdyn\_addressbuildingcompliment
PERSONCHILDRENNAMES | = | msdyn\_childrennames
ADDRESSCITY | = | msdyn\_addresscity
ADDRESSCOUNTRYREGIONID | = | msdyn\_addresscountryregionid
ADDRESSCOUNTRYREGIONISOCODE | = | msdyn\_addresscountryregionisocode
ADDRESSCOUNTYID | = | msdyn\_addresscountyid
CREDITRATING | = | msdyn\_creditrating
ADDRESSDESCRIPTION | = | msdyn\_addressdescription
ADDRESSDISTRICTNAME | = | msdyn\_addressdistrictname
DUNSNUMBER | = | msdyn\_dunsnumber
ETHNICORIGINID | = | msdyn\_ethnicorigin
FORMATTEDPRIMARYADDRESS | = | msdyn\_formattedprimaryaddress
PERSONHOBBIES | = | msdyn\_hobbies
PERSONINITIALS | = | msdyn\_initials
LANGUAGEID | = | msdyn\_languageid
PERSONLASTNAMEPREFIX | = | msdyn\_lastnameprefix
PERSONMIDDLENAME | = | msdyn\_middlename
ORGANIZATIONNUMBER | = | msdyn\_organizationnumber
OURACCOUNTNUMBER | = | msdyn\_ourvendoraccountnumber
PAYMENTID | = | msdyn\_paymentid
PERSONPHONETICFIRSTNAME | = | msdyn\_phoneticfirstname
PERSONPHONETICMIDDLENAME | = | msdyn\_phoneticmiddlename
PERSONPHONETICLASTNAME | = | msdyn\_phoneticlastname
ORGANIZATIONPHONETICNAME | = | msdyn\_organizationphoneticname
ADDRESSPOSTBOX | = | msdyn\_addresspostbox
PRIMARYURL | = | msdyn\_primarycontacturl
PRIMARYEMAILADDRESS | = | msdyn\_primaryemailaddress
PRIMARYEMAILADDRESSDESCRIPTION | = | msdyn\_primaryemailaddressdescription
PRIMARYFACEBOOK | = | msdyn\_primaryfacebook
PRIMARYFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYFAXNUMBER | = | msdyn\_primaryfaxnumber
PRIMARYFAXNUMBERDESCRIPTION | = | msdyn\_primaryfaxnumberdescription
PRIMARYFAXNUMBEREXTENSION | = | msdyn\_primaryfaxnumberextension
PRIMARYLINKEDIN | = | msdyn\_primarylinkedin
PRIMARYLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescription
PRIMARYPHONENUMBER | = | msdyn\_pimaryphonenumber
PRIMARYPHONENUMBERDESCRIPTION | = | msdyn\_primaryphonenumberdescription
PRIMARYPHONENUMBEREXTENSION | = | msdyn\_primaryphonenumberextension
PRIMARYTELEX | = | msdyn\_primarytelex
PRIMARYTELEXDESCRIPTION | = | msdyn\_primarytelexdescription
PRIMARYTWITTER | = | msdyn\_primarytwitter
PRIMARYTWITTERDESCRIPTION | = | msdyn\_primarytwitterdescription
PRIMARYURLDESCRIPTION | = | msdyn\_primaryurldescription
PERSONPROFESSIONALSUFFIX | = | msdyn\_professionalsuffix
PERSONPROFESSIONALTITLE | = | msdyn\_professionatitle
ADDRESSSTATEID | = | msdyn\_addressstateid
ADDRESSSTREET | = | msdyn\_addressstreet
ADDRESSSTREETNUMBER | = | msdyn\_addressstreetnumber
VENDORKNOWNASNAME | = | msdyn\_vendorknownasname
ADDRESSZIPCODE | = | msdyn\_addresszipcode
DEFAULTPAYMENTDAYNAME | = | msdyn\_defaultpaymentdayname.msdyn\_name
DEFAULTPAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
DEFAULTPAYMENTTERMSNAME | = | msdyn\_paymentterms.msdyn\_name
HASONLYTAKENBIDS | \>\< | msdyn\_hasonlytakenbids
ISMINORITYOWNED | \>\< | msdyn\_isminorityowned
ISVENDORLOCALLYOWNED | \>\< | msdyn\_isvendorlocallyowned
ISSERVICEVETERANOWNED | \>\< | msdyn\_isserviceveteranowned
ISOWNERDISABLED | \>\< | msdyn\_ownerisdisabled
ISWOMANOWNER | \>\< | msdyn\_womanowner
PERSONANNIVERSARYDAY | = | msdyn\_personanniversaryday
PERSONANNIVERSARYYEAR | = | msdyn\_anniversaryyear
PERSONBIRTHDAY | = | msdyn\_birthday
PERSONBIRTHYEAR | = | msdyn\_birthyear
ORGANIZATIONEMPLOYEEAMOUNT | = | msdyn\_numberofemployees
VENDORHOLDRELEASEDATE | = | msdyn\_vendoronholdreleasedate
VENDORPARTYNUMBER | = | msdyn\_vendorpartynumber
ADDRESSLOCATIONID | = | msdyn\_addresslocationid
PERSONANNIVERSARYMONTH | = | msdyn\_vendorpersonanniversarymonth
PERSONBIRTHMONTH | = | msdyn\_vendorpersonbirthmonth
PERSONMARITALSTATUS | \>\< | msdyn\_maritalstatus
ADDRESSLATITUDE | \>\> | msdyn\_addresslatitude
ADDRESSLONGITUDE | \>\> | msdyn\_addresslongitude
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
CURRENCYCODE | = | msdyn\_currencycode.isocurrencycode
ISVENDORLOCATEDINHUBZONE | \>\< | msdyn\_isvendorlocatedinhubzone
DEFAULTVENDORPAYMENTMETHODNAME | = | msdyn\_vendorpaymentmethod.msdyn\_name
INVOICEVENDORACCOUNTNUMBER | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
PERSONGENDER | \>\< | msdyn\_gender
AREPRICESINCLUDINGSALESTAX | \>\< | msdyn\_priceincludessalestax
SALESTAXGROUPCODE | = | msdyn\_taxgroup.msdyn\_name
VENDORPRICETOLERANCEGROUPID | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Contacts

Ce modèle synchronise toutes les informations de contact principales, secondaires et tertiaires, pour les clients et les fournisseurs, entre les applications Finance and Operations et les autres applications Dynamics 365. Pour les détails de la mise en correspondance d'entités, voir [Données principales client intégrées](dual-write-customer.md#contacts).

## <a name="vendor-groups"></a>Groupes de fournisseurs

Ce modèle synchronise les informations de groupe de fournisseurs entre les applications Finance and Operations et d'autres applications Dynamics 365.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
DEFAULTPAYMENTTERMNAME | = | msdyn\_paymentterms.msdyn\_name
DESCRIPTION | = | msdyn\_description
VENDORGROUPID | = | msdyn\_vendorgroup
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Mode de paiement fournisseur

Ce modèle synchronise les informations de mode de paiement fournisseur entre Finance and Operations et d'autres applications Dynamics 365.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | = | msdyn\_name
DESCRIPTION | = | msdyn\_description
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
ALLOWPAYMENTCOPIES | \>\< | msdyn\_allowpaymentcopies
PAYMENTTYPE | \>\< | msdyn\_paymenttype
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
ACCOUNTTYPE | \>\< | msdyn\_accounttype
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingposting
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_postdatedcheckclearingposting
PROMISSORYNOTEDRAFTTYPE | \>\< | msdyn\_promissorynotedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

