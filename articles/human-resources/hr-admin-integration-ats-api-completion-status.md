---
title: État d’achèvement
description: Cet article décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 32575dfdd9bcd61b8a16bb544a9e7906ec96eaa1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880565"
---
# <a name="completion-status"></a>État d’achèvement


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’option État d’achèvement définie pour Dynamics 365 Human Resources.

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
