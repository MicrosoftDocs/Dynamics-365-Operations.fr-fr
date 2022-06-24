---
title: Date de début pour le calcul de la fréquence de filtrage
description: Cet article décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 846a35a2e8ca39ed9479601d99c8c515328d8ce5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879306"
---
# <a name="screening-frequency-generate-from"></a>Date de début pour le calcul de la fréquence de filtrage


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmfrequencygeneratefrom

Cette énumération fournit le jeu d’options de valeurs pour déterminer la date de début du calcul pour la prochaine présélection obligatoire.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 Non sélectionné | Aucune valeur n’a été sélectionnée. |
| 200000001 Date de fin | Le calcul est effectué à partir de la dernière date des tests. |
| 200000002 Date obligatoire | Le calcul est effectué à partir de la dernière date des tests obligatoires. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
