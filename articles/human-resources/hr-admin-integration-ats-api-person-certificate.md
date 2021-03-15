---
title: Certificat de la personne
description: Cette rubrique décrit l'entité Certificat de la personne pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa4582dc00341a647f1ea43ed16d9dce8bfcf688
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125351"
---
# <a name="person-certificate"></a>Certificat de la personne

Cette rubrique décrit l'entité Certificat de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersoncertificateentity

## <a name="description"></a>Description

Cette entité décrit les certificats professionnels d'un candidat.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d'entité de certificat de la personne**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour le dossier d'entité de certificat de la personne. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | ID de tiers (personne) du candidat. |
| **Valeur de l'ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l'entité mshr_dirpersonentity | Identificateur généré par le système de l'enregistrement de l'entité de tiers (personne). |
| **ID de type de certificat**<br>mshr_certificatetypeid<br>*Chaîne* | Lecture/écriture<br>Requis |  Identifiant du type de certificat défini dans Human Resources. |
| **Valeur de l'ID de type de certificat**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmcertificatetypeentityid de l'entité mshr_hcmcertificatetypeentity | Identificateur unique généré par le système du type de certificat de l'entité associée. |
| **Date de début**<br>mshr_startdate<br>*DateHeure* | Lecture/écriture<br>Requis | Date à laquelle le certificat a été délivré. |
| **Date de fin**<br>mshr_enddate<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date à laquelle le certificat va expirer. |
| **Notes**<br>mshr_notes<br>*Chaîne* | Lecture/écriture<br>Facultatif | Notes à l'intention des recruteurs et des responsables du recrutement. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis |  Champ à utiliser comme identifiant principal de l'enregistrement d'entité. Combinaison du numéro de tiers, de l'ID du type de certificat et de la date de début. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l'entité Candidat à l'embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]