---
title: Contact du tiers
description: Cette rubrique décrit l’entité Contact du tiers pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: b37910f10c0d89e2659aa0bfbdc601c3592f896c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053801"
---
# <a name="party-contact"></a>Contact du tiers

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Contact du tiers pour Dynamics 365 Human Resources.

Nom physique : mshr_dirpartycontactentities

## <a name="description"></a>Description

Cette entité décrit les informations de contact du candidat, y compris les adresses e-mail, les numéros de téléphone et les comptes de réseaux sociaux.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité de contact tiers**<br>mshr_dirpartycontactentityid<br>*Chaîne* | Lecture seule<br>Requis | Identificateur unique généré par le système pour l’enregistrement d’entité. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | L’ID de l’enregistrement de tiers (personne) associé. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity | Identificateur généré par le système de l’enregistrement de l’entité de tiers (personne). |
| **ID emplacement**<br>mshr_locationid<br>*Chaîne* | Lecture/écriture<br>Requis | ID d’emplacement de l’enregistrement d’adresse. Configuré dans l’entité mshr_logisticspostaladdresslocationcdsentity. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Description des coordonnées. |
| **Type**<br>mshr_type<br>*Jeu d’options mshr_logisticselectronicaddressmethodtype* | Lecture/écriture<br>Requis | Type de détail du contact. |
| **Code Pay Région**<br>mshr_countryregioncode<br>*Chaîne* | Lecture/écriture<br>Facultatif | Pays ou région de l’adresse. |
| **Localisateur**<br>mshr_locator<br>*Chaîne* | Lecture/écriture<br>Facultatif | Détails du contact. Par exemple, si le type est **Adresse e-mail**, alors ce champ contient l’adresse e-mail du candidat. |
| **Extension de localisateur**<br>mshr_locatorextension<br>*Chaîne* | Lecture/écriture<br>Facultatif | Extension du localisateur. Par exemple, si le type est **Téléphone**, alors cette propriété contiendra l’extension du numéro de téléphone. |
| **Est un portable**<br>mshr_ismobile<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Spécifie si le téléphone est un numéro de mobile. |
| **Est un message instantané**<br>mshr_isinstantmessage<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Spécifie si le téléphone est activé pour la messagerie instantanée. |
| **Est principal**<br>mshr_isprimary<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Détermine le contact principal du type de contact. Il ne doit y avoir qu’un seul enregistrement principal par type de contact. |
| **Est privé**<br>mshr_isprivate<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Identifie si cette adresse est une adresse privée pour la personne. |
| **Objectif**<br>mshr_purpose<br>*Chaîne* | Lecture/écriture<br>Facultatif | Objectif/rôle des coordonnées. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ utilisé comme identifiant principal de l’enregistrement d’entité. Combinaison de numéro de tiers, type, description et localisateur. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]