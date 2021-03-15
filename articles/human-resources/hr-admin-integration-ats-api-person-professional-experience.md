---
title: Expérience professionnelle de la personne
description: Cette rubrique décrit l'entité Expérience professionnelle de la personne pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 51dd993e2d43174e96c062e142021cc0f6e3a288
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125279"
---
# <a name="person-professional-experience"></a>Expérience professionnelle de la personne

Cette rubrique décrit l'entité Expérience professionnelle de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>Description

Cette entité décrit l'expérience professionnelle ou les antécédents professionnels d'un candidat.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d'entité Expérience professionnelle de la personne**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour l'enregistrement d'entité. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | Identificateur unique du dossier du candidat. |
| **Valeur de l'ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l'entité mshr_dirpersonentity | Identificateur unique généré par le système pour le dossier d'entité de la personne. |
| **Poste de l'employeur**<br>mshr_employerposition<br>*Chaîne* | Lecture/écriture<br>Requis | Intitulé du poste occupé par le candidat pendant son emploi. |
| **Nom de l’employeur**<br>mshr_employername<br>*Chaîne* | Lecture/écriture<br>Requis | Nom de l'employeur. |
| **Emplacement de l'employeur**<br>mshr_employerlocation<br>*Chaîne* | Lecture/écriture<br>Facultatif | Emplacement de l'employeur. Longueur max. : 60. Aucun format spécifique défini ou requis. |
| **Téléphone**<br>mshr_phone<br>*Chaîne* | Lecture/écriture<br>Facultatif | Numéro de téléphone de l'employeur. |
| **URL**<br>mshr_url<br>*Chaîne* | Lecture/écriture<br>Facultatif | URL du site Web de l'employeur. |
| **Date de début**<br>mshr_startdate<br>*DateHeure* | Lecture/écriture<br>Requis | Date de début de l'emploi du candidat. |
| **Date de fin**<br>mshr_enddate<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date de fin de l'emploi du candidat, ou Null si le candidat est toujours employé ici. |
| **Autoriser à contacter l'employeur**<br>mshr_allowcontactemployer<br>*Jeu d'options mshr_hrmblankyesno* | Lecture/écriture<br>Facultatif | Indique si le candidat autorise à contacter l'ancien employeur. |
| **Notes**<br>mshr_note<br>*Chaîne* | Lecture/écriture<br>Facultatif | Notes à l'intention du recruteur ou du responsable du recrutement. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ utilisé comme identifiant principal de l'enregistrement d'entité. Combinaison du numéro de tiers, de la date de début, du poste de l'employeur et du nom de l'employeur. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l'entité Candidat à l'embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]