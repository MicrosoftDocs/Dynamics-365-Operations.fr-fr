---
title: Personne
description: Cette rubrique décrit l’entité Personne pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 448be7ada2825d3cdd846650821579d1d6797d00
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800355"
---
# <a name="person"></a>Personne

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Personne pour Dynamics 365 Human Resources.

Nom physique : mshr_dirpersonentity

### <a name="description"></a>Description

Cette entité fournit les informations personnelles de l’individu qui est le candidat.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité de la personne**<br>mshr_dirpersonentityid<br>*GUID* | Lecture seule<br>Requis<br>Généré par le système | Identificateur unique généré par le système pour l’enregistrement d’entité. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture seule<br>Requis<br>Généré par le système | Identificateur unique généré par le système, lisible par l’utilisateur pour la personne.  |
| **Nom**<br>mshr_name<br>*Chaîne* | Lecture seule<br>Requis | La valeur du champ est une concaténation du prénom, du deuxième prénom, du préfixe du nom et du nom dans l’ordre défini dans le champ **Ordre d’affichage du nom**. |
| **Alias de nom**<br>mshr_namealias<br>*Chaîne* | Lecture/écriture<br>Facultatif | Alias de nom qui peut être fourni pour la personne. |
| **Nom d’usage**<br>mshr_knownas<br>*Chaîne* | Lecture/écriture<br>Facultatif | Nom qui peut être utilisé pour la personne si elle est connue sous un autre nom. |
| **ID langue**<br>mshr_languageid<br>*Chaîne* | Lecture/écriture<br>Facultatif | ID de langue de la langue principale de la personne, tel que défini au format ISO 639-1. |
| **Carnets d’adresses**<br>mshr_addressbooks<br>*Chaîne* | Lecture/écriture<br>Facultatif | Carnet d’adresses auquel la personne peut être affectée. Les carnets d’adresses qui ont été configurés pour l’organisation sont répertoriés dans l’entité mshr_diraddressbooksentity. |
| **Jour d’anniversaire**<br>mshr_anniversaryday<br>*Int* | Lecture/écriture<br>Facultatif | Le jour de la date anniversaire de la personne. |
| **Mois d’anniversaire**<br>mshr_anniversarymonth<br>*Jeu d’options mshr_monthsofyear* | Lecture/écriture<br>Facultatif | Le mois de la date anniversaire de la personne. |
| **Année d’anniversaire**<br>mshr_anniversaryyear<br>*Int* | Lecture/écriture<br>Facultatif | L’année de la date anniversaire de la personne. |
| **Jour de naissance**<br>mshr_birthday<br>*Int* | Lecture/écriture<br>Facultatif | Le jour de la naissance de la personne. |
| **Mois de naissance**<br>mshr_birthmonth<br>*Jeu d’options mshr_monthsofyear* | Lecture/écriture<br>Facultatif | Le mois de naissance de la personne. |
| **Année de naissance**<br>mshr_birthyear<br>*Int* | Lecture/écriture<br>Facultatif | L’année de naissance de la personne. |
| **Nom des enfants**<br>mshr_childrennames<br>*Chaîne* | Lecture/écriture<br>Facultatif | Chaîne pour le nom des enfants de la personne. Il n’y a pas de délimitation requise. |
| **Sexe**<br>mshr_gender<br>*Jeu d’options mshr_hcmpersongender* | Lecture/écriture<br>Facultatif | Sexe de la personne. |
| **Loisirs**<br>mshr_hobbies<br>*Chaîne* | Lecture/écriture<br>Facultatif | Loisirs de la personne. |
| **Initiales**<br>mshr_initials<br>*Chaîne* | Lecture/écriture<br>Facultatif | Les initiales du nom de la personne. |
| **Situation de famille**<br>mshr_maritalstatus<br>*Jeu d’options mshr_hcmpersonmaritalstatus* | Lecture/écriture<br>Facultatif | État civil de la personne. |
| **Prénom phonétique**<br>mshr_phoneticfirstname<br>*Chaîne* | Lecture/écriture<br>Facultatif | La prononciation phonétique du prénom de la personne. |
| **Nom phonétique**<br>mshr_phoneticlastname<br>*Chaîne* | Lecture/écriture<br>Facultatif | La prononciation phonétique du nom de la personne. |
| **Deuxième prénom phonétique**<br>mshr_phoneticmiddlename<br>*Chaîne* | Lecture/écriture<br>Facultatif | La prononciation phonétique du nom de la personne. |
| **Suffixe personnel**<br>mshr_personalsuffix<br>*Chaîne* | Lecture/écriture<br>Facultatif | Le suffixe personnel de la personne. Valeurs valides dans l’entité mshr_dirnameaffixentity où mshr_type est le suffixe (200000001). |
| **Titre de civilité**<br>mshr_personaltitle<br>*Chaîne* | Lecture/écriture<br>Facultatif | Titre de civilité de la personne. Valeurs valides dans l’entité mshr_dirnameaffixentity où mshr_type est Titre (200000000).
| **Suffixe professionnel**<br>mshr_professionalsuffix<br>*Chaîne* | Lecture/écriture<br>Facultatif | Suffixe professionnel. |
| **Fonction professionnelle**<br>mshr_professionaltitle<br>*Chaîne* | Lecture/écriture<br>Facultatif | Fonction professionnelle. |
| **Adresse principale complète**<br>mshr_fullprimaryaddress<br>*Chaîne* | Lecture/écriture<br>Facultatif | L’adresse principale complète de la personne, une concaténation des champs d’adresse principale. |
| **Adresse – Ville**<br>mshr_addresscity<br>*Chaîne* | Lecture/écriture<br>Facultatif | La ville de l’adresse principale de la personne. Configuré dans l’entité mshr_logisticsaddresscityentity. |
| **Adresse Pays Région**<br>mshr_addresscountryregionid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Pays/région de l’adresse principale de la personne. Valeurs valides dans l’entité mshr_logisticsaddresscountryregionentity. |
| **Code ISO Adresse Pays Région**<br>mshr_addresscountryregionisocode<br>*Chaîne* | Lecture/écriture<br>Facultatif | Code ISO de l’adresse principale de la personne. |
| **Adresse Département**<br>mshr_addresscounty<br>*Chaîne* | Lecture/écriture<br>Facultatif | Le département de l’adresse principale de la personne. Configuré dans l’entité mshr_logisticsaddresscountyentity. |
| **Nom de l’adresse du secteur**<br>mshr_addressdistrictname<br>*Chaîne* | Lecture/écriture<br>Facultatif | Secteur de l’adresse principale de la personne. Configuré dans l’entité mshr_logisticsaddressdistrictentity. |
| **Latitude de l’adresse**<br>mshr_addresslatitude<br>*Chaîne* | Lecture/écriture<br>Facultatif | Latitude de l’adresse principale de la personne. |
| **ID d’emplacement d’adresse**<br>mshr_addresslocationid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Identificateur unique de l’emplacement de l’adresse principale de la personne. Valeurs valides dans l’entité mshr_logisticspostaladdresslocationcdsentity. |
| **Rôles de l’emplacement de l’adresse**<br>mshr_addresslocationroles<br>*Chaîne* | Lecture/écriture<br>Facultatif | Rôle de l’emplacement de l’adresse principale de la personne. Configuré dans l’entité mshr_logisticslocationrolecdsentity. |
| **Longitude de l’adresse**<br>mshr_addresslongitude<br>*Chaîne* |  Lecture/écriture<br>Facultatif | Longitude de l’adresse principale de la personne. |
| **État de l’adresse**<br>mshr_addressstate<br>*Chaîne* | Lecture/écriture<br>Facultatif | L’état de l’adresse principale de la personne. Configuré dans l’entité mshr_logisticsaddressstateentity. |
| **Rue de l’adresse**<br>mshr_addressstreet<br>*Chaîne* | Lecture/écriture<br>Facultatif | Rue de l’adresse principale de la personne. |
| **Adresse valide à partir du**<br>mshr_addressvalidfrom<br>*Date* | Lecture/écriture<br>Facultatif | Date à partir de laquelle l’adresse principale de la personne est valide. |
| **Adresse valide jusqu’au**<br>mshr_addressvalidto<br>*Date* | Lecture/écriture<br>Facultatif | Date jusqu’à laquelle l’adresse principale de la personne est valide. |
| **Code postal de l’adresse**<br>mshr_addresszipcode<br>*Chaîne* | Lecture/écriture<br>Facultatif | Code postal de l’adresse principale de la personne. Configuré dans l’entité mshr_logisticsaddresspostalcodeentity. |
| **Adresse privée**<br>mshr_addressisprivate<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Détermine si l’adresse principale de la personne est partagée avec d’autres utilisateurs de l’organisation. |
| **Description de l’adresse**<br>mshr_addressdescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour l’adresse principale de la personne. |
| **E-mail principal de contact**<br>mshr_primarycontactemail<br>*Chaîne* | Lecture/écriture<br>Facultatif | Adresse e-mail principale de la personne. |
| **Description de l’e-mail du contact principal**<br>mshr_primarycontactemaildescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour l’adresse e-mail principale. |
| **E-mail principal de contact est IM**<br>mshr_primarycontactemailisim<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Détermine si l’adresse e-mail principale est disponible pour les messages instantanés. |
| **Objectif de l’e-mail du contact principal**<br>mshr_primarycontactemailpurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif de l’adresse e-mail principale. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **Télécopie du contact principal**<br>mshr_primarycontactfax<br>*Chaîne* | Lecture/écriture<br>Facultatif | Numéro de télécopie principal. |
| **Description de la télécopie du contact principal**<br>mshr_primarycontactfaxdescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour le numéro de télécopie principale. |
| **Extension de la télécopie du contact principal**<br>mshr_primarycontactfaxextension<br>*Chaîne* | Lecture/écriture<br>Facultatif | Extension du numéro de télécopie principal. |
| **Objectif de la télécopie du contact principal**<br>mshr_primarycontactfaxpurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif du numéro de télécopie principal. Configuré dans l’entité mshr_logisticslocationroleentity.
| **Numéro de téléphone principal**<br>mshr_primarycontactphone<br>*Chaîne* | Lecture/écriture<br>Facultatif | Numéro de téléphone principal. |
| **Description du numéro de téléphone principal**<br>mshr_primarycontactphonedescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour le numéro de téléphone principal. |
| **Extension du numéro de téléphone principal**<br>mshr_primarycontactphoneextension<br>*Chaîne* | Lecture/écriture<br>Facultatif | Extension du numéro de téléphone principal. |
| **Numéro de téléphone principal est mobile**<br>mshr_primarycontactphoneismobile<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Détermine si le numéro de téléphone principal est un téléphone mobile. |
| **Objectif du numéro de téléphone principal**<br>mshr_primarycontactphonepurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | L’objectif du numéro de téléphone principal. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **Telex du contact principal**<br>mshr_primarycontacttelex<br>*Chaîne* | Lecture/écriture<br>Facultatif | Numéro de télex principal. |
| **Description du télex du contact principal**<br>mshr_primarycontacttelexdescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour le numéro de télex principal de la personne. |
| **Objectif du télex du contact principal**<br>mshr_primarycontacttelexpurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif du numéro de télex principal de la personne. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **URL du contact principal**<br>mshr_primarycontacturl<br>*Chaîne* | Lecture/écriture<br>Facultatif | URL principale. |
| **Description de l’URL du contact principal**<br>mshr_primarycontacturldescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour l’URL principale de la personne. |
| **Objectif de l’URL du contact principal**<br>mshr_primarycontacturldescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif de l’URL principale de la personne. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **Contact Facebook principal**<br>mshr_primarycontactfacebook<br>*Chaîne* | Lecture/écriture<br>Facultatif | Compte Facebook principal. Identifié par ID utilisateur. |
| **Description du contact Facebook principal**<br>mshr_primarycontactfacebookdescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour le compte Facebook principal de la personne. |
| **Contact Facebook principal est Privé**<br>mshr_primarycontactfacebookisprivate<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Détermine si le compte Facebook principal est visible par les autres utilisateurs. |
| **Objectif du contact Facebook principal**<br>mshr_primarycontactfacebookpurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif du compte Facebook principal de la personne. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **Contact LinkedIn principal**<br>mshr_primarycontactlinkedin<br>*Chaîne* | Lecture/écriture<br>Facultatif | Compte LinkedIn principal. Identifié par le nom d’utilisateur. |
| **Description du contact LinkedIn principal**<br>mshr_primarycontactlinkedindescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour le compte LinkedIn principal de la personne. |
| **Contact LinkedIn principal est Privé**<br>mshr_primarycontactlinkedinisprivate<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Détermine si les informations principales du compte LinkedIn de la personne sont partagées avec d’autres utilisateurs. |
| **Objectif du contact LinkedIn principal**<br>mshr_primarycontactlinkedinpurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif du compte LinkedIn principal de la personne. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **Contact Twitter principal**<br>mshr_primarycontacttwitter<br>*Chaîne* | Lecture/écriture<br>Facultatif | Compte Twitter principal de la personne. Identifié par @username. |
| **Description du contact Twitter principal**<br>mshr_primarycontacttwitterdescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description fournie pour le compte Twitter principal de la personne. |
| **Contact Twitter principal est Privé**<br>mshr_primarycontacttwitterisprivate<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Détermine si les informations principales du compte Twitter de la personne sont partagées avec d’autres utilisateurs. |
| **Objectif du compte Twitter du contact principal**<br>mshr_primarycontacttwitterpurpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif du compte Twitter principal de la personne. Configuré dans l’entité mshr_logisticslocationroleentity. |
| **Type de tiers**<br>mshr_partytype<br>*Chaîne* | Lecture/écriture<br>Facultatif | Le type de la personne. Sera toujours **Personne** pour les candidats. |
| **Ordre d’affichage du nom**<br>mshr_namesequencedisplayas<br>*Chaîne* | Lecture/écriture<br>Facultatif | Séquence dans laquelle les propriétés du nom de la personne sont concaténées à partir de la valeur de la propriété Nom (mshr_name). |
| **Prénom**<br>mshr_firstname<br>*Chaîne* | Lecture/écriture<br>Requis | Prénom de la personne. |
| **Deuxième prénom**<br>mshr_middlename<br>*Chaîne* | Lecture/écriture<br>Facultatif | Deuxième prénom de la personne. |
| **Préfixe du nom**<br>mshr_lastnameprefix<br>*Chaîne* | Lecture/écriture<br>Facultatif | Préfixe du nom de famille de la personne. |
| **Nom**<br>mshr_lastname<br>*Chaîne* | Lecture/écriture<br>Facultatif | Nom de la personne. |
| **ID de localisation électronique**<br>mshr_electroniclocationid<br>*Chaîne* | Lecture/écriture<br>Facultatif | ID de l’emplacement électronique de la personne. |
| **Fuseau horaire de l’adresse**<br>mshr_addresstimezone<br>*Int* | Lecture/écriture<br>Facultatif | Fuseau horaire de l’adresse principale de la personne. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]