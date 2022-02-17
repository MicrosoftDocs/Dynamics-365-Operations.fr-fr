---
title: Adresse de la personne
description: Cette rubrique décrit l’entité Adresse de la personne pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d428c2b1ce69c55fda2e574715021d4763544a6b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065475"
---
# <a name="person-address"></a>Adresse de la personne


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Adresse de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersonaddressentities

## <a name="description"></a>Description

Cette entité contient la liste des adresses postales des dossiers de candidature.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité d’adresse de personne**<br>mshr_hcmpersonaddressentityid<br>*Chaîne* | Lecture seule<br>Requis | Identificateur unique généré par le système pour l’enregistrement d’entité. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | L’ID de l’enregistrement de tiers (personne) associé. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity | Identificateur généré par le système de l’enregistrement de l’entité de tiers (personne). |
| **ID emplacement**<br>mshr_locationid<br>*Chaîne* | Lecture/écriture<br>Requis | ID d’emplacement de l’enregistrement d’adresse. Configuré dans l’entité mshr_logisticspostaladdresslocationcdsentity. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Description de l’adresse du candidat. |
| **Rôles**<br>mshr_roles<br>*Chaîne* | Lecture/écriture<br>Requis | Rôles attribués à cette adresse. Plusieurs rôles peuvent être attribués. Chaque rôle doit être séparé par un point-virgule. Valeurs valides contenues dans l’entité mshr_logisticslocationroleentity. |
| **Rue**<br>mshr_street<br>*Chaîne* | Lecture/écriture<br>Facultatif | Numéro de la rue. |
| **Ville**<br>mshr_city<br>*Chaîne* | Lecture/écriture<br>Facultatif | Ville de l’adresse. Configuré dans l’entité mshr_logisticsaddresscityentity. |
| **État**<br>mshr_state<br>*Chaîne* | Lecture/écriture<br>Facultatif | État de l’adresse. Configuré dans l’entité mshr_logisticsaddressstateentity. |
| **Département**<br>mshr_county<br>*Chaîne* | Lecture/écriture<br>Facultatif | Département de l’adresse. Configuré dans l’entité mshr_logisticsaddresscountyentity. |
| **Code postal**<br>mshr_zipcode<br>*Chaîne* | Lecture/écriture<br>Facultatif | Code postal de l’adresse. Configuré dans l’entité mshr_logisticsaddresspostalcodeentity. |
| **ID pays/région**<br>mshr_countryregionid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Pays ou région de l’adresse. |
| **Valeur de l’ID pays/région**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_logisticaddresscountryregionentityid de l’entité mshr_logisticsaddresscountryregionentity | Identificateur unique généré par le système du pays ou de la région de l’adresse. |
| **Est principal**<br>mshr_isprimary<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Identifie si cette adresse est l’adresse principale de la personne du rôle défini. |
| **Est privé**<br>mshr_isprivate<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Identifie si cette adresse est une adresse privée pour la personne. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ utilisé comme identifiant principal de l’enregistrement d’entité. Combinaison du numéro de tiers et de l’ID d’emplacement. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
