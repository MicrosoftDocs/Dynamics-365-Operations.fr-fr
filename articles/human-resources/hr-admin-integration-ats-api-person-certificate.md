---
title: Certificat de la personne
description: Cet article décrit l’entité Certificat de la personne pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/15/2022
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
ms.openlocfilehash: 1f9d5a8c83d9714a4d10dec16e66ab87b794b074
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887315"
---
# <a name="person-certificate"></a>Certificat de la personne


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité Certificat de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersoncertificateentity

## <a name="description"></a>Description

Cette entité décrit les certificats professionnels d’un candidat.

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

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID de type de certificat**<br>mshr_certificatetypeid<br>*Chaîne* | Lecture/écriture<br>Requis |  Identifiant du type de certificat défini dans Human Resources. |
| **Date de début**<br>mshr_startdate<br>*DateHeure* | Lecture/écriture<br>Obligatoire | Date à laquelle le certificat a été délivré. |
| **Date de fin**<br>mshr_enddate<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date à laquelle le certificat va expirer. |
| **Notes**<br>mshr_notes<br>*Chaîne* | Lecture/écriture<br>Facultatif | Notes à l’intention des recruteurs et des responsables du recrutement. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Obligatoire | ID de tiers (personne) du candidat. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Obligatoire |  Champ à utiliser comme identifiant principal de l’enregistrement d’entité. Combinaison du numéro de tiers, de l’ID du type de certificat et de la date de début. |
| **Valeur de l’ID de type de certificat**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmcertificatetypeentityid de l’entité mshr_hcmcertificatetypeentity | Identificateur unique généré par le système du type de certificat de l’entité associée. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity | Identificateur généré par le système de l’enregistrement de l’entité de tiers (personne). |
| **ID d’entité de certificat de la personne**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour le dossier d’entité de certificat de la personne. |




## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
