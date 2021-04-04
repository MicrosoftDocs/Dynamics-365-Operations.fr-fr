---
title: Présélection
description: Cette rubrique décrit l’entité Présélection pour Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6287f30aaa008ea77b91fd46a8dfb2b7c905036
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467239"
---
# <a name="person-screening"></a>Présélection

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Présélection pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersonscreeningentity

## <a name="description"></a>Description

Cette entité décrit les présélections qu’un candidat a réussies ou doit réussir pour le poste.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité de présélection**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Lecture seule<br>Requis<br>Généré par le système | Identificateur principal unique pour le dossier de présélection. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | Le numéro tiers (personne) associé au candidat. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity | Identificateur généré par le système de l’enregistrement de l’entité de tiers (personne). |
| **ID type de présélection**<br>mshr_screeningtypeid<br>*Chaîne* | Lecture/écriture<br>Requis<br>Clé étrangère : ScreeningType | Identifiant du type de présélection défini dans Human Resources. |
| **Valeur de l’ID de type de présélection**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmscreeningtypeentityid de l’entité mshr_hcmscreeningtypeentity | Identificateur généré par le système pour le dossier du type de présélection de l’entité associée. |
| **Requis par**<br>mshr_requiredby<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date à laquelle la présélection doit être terminée. |
| **État**<br>mshr_status<br>*Jeu d’options mshr_hcmcompletionstatus*<br>Lecture/écriture<br>Requis | Fournit le statut du candidat pour la présélection. |
| **Date de fin**<br>mshr_completeddate<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date à laquelle la présélection s’est terminée. |
| **Notes**<br>mshr_note<br>*Chaîne* | Lecture/écriture<br>Facultatif | Notes à l’intention des recruteurs et des responsables du recrutement. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]