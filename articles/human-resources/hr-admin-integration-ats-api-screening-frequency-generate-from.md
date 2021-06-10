---
title: Date de début pour le calcul de la fréquence de présélection
description: Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: ae5ad3e556f40cedd385d8aadded9ef76447a98b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054090"
---
# <a name="screening-frequency-generate-from"></a>Date de début pour le calcul de la fréquence de présélection

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.

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