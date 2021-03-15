---
title: Numéro d'identification de la personne
description: Cette rubrique décrit l'entité Numéro d'identification de la personne pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 054547c4f33e50d2dc0fa275559ba6ed44c27971
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125399"
---
# <a name="person-identification-number"></a>Numéro d'identification de la personne

Cette rubrique décrit l'entité Numéro d'identification de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>Description

Cette entité décrit le numéro d'identification du candidat. Elle permet au consommateur d'API d'écrire des numéros d'identification, tels que des numéros de sécurité sociale ou des numéros de passeport, dans le dossier du candidat. Les numéros d'identification figurent sur le dossier du collaborateur, mais pas sur le dossier du candidat. Une application d'intégration peut écrire les valeurs dans la base de données Human Resources, mais ces chiffres ne seront pas visibles dans Human Resources tant que le dossier du candidat n'est pas créé.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Person Identification Number Entity ID**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Lecture seule<br>Requis<br>Généré par le système | Identificateur principal unique pour le dossier du numéro d'identification de la personne. |
| **Type de saisie**<br>mshr_entrytype<br>*Chaîne* | Lecture/écriture<br>Facultatif | Valeur libre pour référencer le type d'entrée pour le numéro d'identification. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description du numéro d'identification. |
| **Date d'expiration**<br>mshr_expirationdate<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date à laquelle le numéro d'identification ou le document associé expire. |
| **Est principal**<br>mshr_isprimary<br>*Jeu d'options mshr_noyes* | Lecture/écriture<br>Facultatif | Définit si le numéro d'identification est l'enregistrement principal de la personne pour ce type d'identification. |
| **Numéro d'identification**<br>mshr_identificationnumber<br>*Chaîne* | Lecture/écriture<br>Requis | Numéro d'identification. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | Identificateur du tiers (personne) propriétaire du numéro d'identification. |
| **Valeur de l'ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l'entité mshr_dirpersonentity | Identificateur unique du tiers (personne). |
| **ID du type d'identification**<br>mshr_identificationtypeid<br>*Chaîne* | Lecture/écriture<br>Requis | Type du numéro d'identification. |
| **Valeur de l'ID du type d'identification**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmidentificationtypeentityid de l'entité mshr_hcmidentificationtypeentity | Identifiant unique généré par le système du type d'identification. |
| **ID agence émettrice**<br>mshr_issuingagencyid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Agence ou organisation qui a délivré le numéro d'identification. |
| **Valeur d'ID agence émettrice**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmissuingagencyentityid de l'entité mshr_hcmissuingagencyentity | Identifiant unique généré par le système de l'agence émettrice du numéro d'identification. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ à utiliser comme identifiant principal de l'enregistrement d'entité. Combinaison du numéro de tiers, de l'ID du type d'identification et du numéro d'identification. |
| **Date d'émission**<br>mshr_issuedate<br>*Date* | Lecture/écriture<br>Facultatif | Date à laquelle le numéro d'identification a été délivré. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l'entité Candidat à l'embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]