---
title: Type de certificat
description: Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 962bccb3aaab16322d072417660ec3aac821183b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467479"
---
# <a name="certificate-type"></a>Type de certificat

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Type de certificat pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmcertificatetypeentity

## <a name="description"></a>Description

Cette entité définit la liste des types de certificats professionnels mis en place dans Human Resources. L’entité n’est pas spécifique à une entité juridique (entreprise).

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité de type de certificat**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Lecture seule<br>Requis 
Généré par le système | Identificateur principal unique pour le type de certificat. |
| **Type de certificat**<br>mshr_certificatetype<br>*Chaîne* | Lecture/écriture<br>Requis | Identificateur unique lisible par l’utilisateur pour le type de certificat. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Description du type de certificat. |
| **Demander un renouvellement**<br>mshr_requirerenewal<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Facultatif | Indique si le renouvellement est requis pour le certificat. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]