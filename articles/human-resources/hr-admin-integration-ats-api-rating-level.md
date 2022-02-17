---
title: Niveau de classement
description: Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: a821e3cd90e85571da4a09f5dd564beb2de35989
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068632"
---
# <a name="rating-level"></a>Niveau de classement


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Niveau de classement pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmratinglevelentity

## <a name="description"></a>Description

Cette entité fournit les niveaux de notation disponibles pour les compétences. Les niveaux de notation s’appliquent à toutes les entités juridiques.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité de niveau de notation**<br>mshr_hcmratinglevelentityid<br>*GUID* | Lecture seule<br>Requis<br>Généré par le système | Identificateur unique généré par le système pour le niveau. |
| **ID de niveau de classement**<br>mshr_ratinglevelid<br>*Chaîne* | Lecture/écriture<br>Requis | Identificateur unique lisible par l’utilisateur pour le niveau. |
| **ID de modèle de classement**<br>mshr_ratingmodelid<br>*Chaîne* | Lecture/écriture<br>Requis | Modèle de classement auquel appartient le niveau de classement. |
| **ID d’entité de modèle de classement**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmratingmodelentityid de l’entité mshr_hcmratingmodelentity | Identificateur généré par le système pour le modèle d’évaluation auquel appartient le niveau d’évaluation. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Description du niveau de classement. |
| **Facteur**<br>mshr_factor<br>*Entier* | Lecture/écriture<br>Requis | Facteur pour le niveau de classement. Lorsque vous comparez des articles avec un autre nombre de niveaux de classement, le facteur permet de normaliser les scores. La valeur doit être un entier compris entre 0 et 9. |
| **Remarque**<br>mshr_note<br>*Chaîne* | Lecture/écriture<br>Facultatif | Toutes les notes associées au niveau de classement. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ à utiliser comme identifiant principal de l’enregistrement d’entité. Combinaison de l’ID du niveau de classification et de l’ID du modèle de classement. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
