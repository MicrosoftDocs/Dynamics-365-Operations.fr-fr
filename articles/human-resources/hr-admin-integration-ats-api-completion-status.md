---
title: État d’achèvement
description: Cette rubrique décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468201"
---
# <a name="completion-status"></a>État d’achèvement

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmcompletionstatus

Cette énumération fournit le jeu d’options des valeurs de statut pour la présélection des candidats. 

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Incomplet | Le candidat n’a pas encore effectué de présélection. |
| 200000001 | Réussite | Le candidat a réussi la présélection. |
| 200000002 | Échec | Le candidat n’a pas réussi la présélection. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]