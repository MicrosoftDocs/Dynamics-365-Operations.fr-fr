---
title: Types de présélection
description: Cette rubrique décrit l’entité Types de présélection pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: d3a45d802ab6b574338a09e77d432357cb9df507
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465916"
---
# <a name="screening-types"></a>Types de présélection

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Types de présélection pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmscreeningtypeentity

## <a name="description"></a>Description

Cette entité décrit les types de présélection mis en place par l’entreprise pour les processus de présélection avant l’embauche des employés.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID de l’entité de type de présélection**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Lecture seule<br>Requis<br>Généré par le système | Identificateur principal unique de l’enregistrement de type de test. |
| **ID type de présélection**<br>mshr_screeningtypeid<br>*Chaîne* | Lecture/écriture<br>Requis | Identificateur unique défini par l’utilisateur pour le type de présélection. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Description du type de test. |
| **Unité de fréquence**<br>mshr_frequencyunit<br>*Jeu d’options mshr_hcmfrequencyunit* | Lecture/écriture<br>Requis | Décrit la fréquence à laquelle les présélections doivent être effectuées pour la personne désignée. |
| **Date de début pour le calcul**<br>mshr_generatefrom<br>*Jeu d’options mshr_hcmfrequencygeneratefrom* | Lecture/écriture<br>Requis | Si la valeur de fréquence est une valeur autre que Occasionnelle uniquement, la valeur GenerateFrom détermine la date à partir de laquelle calculer le prochain événement de présélection. |
| **Intervalle de fréquence**<br>mshr_frequencyinterval<br>*Entier* | Lecture/écriture<br>Requis | Si la valeur de fréquence est une valeur autre que Occasionnelle uniquement, vous devez définir un intervalle pour les unités de temps entre chaque événement de présélection. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]