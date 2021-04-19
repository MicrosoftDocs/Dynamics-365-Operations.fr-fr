---
title: Date de début pour le calcul de la fréquence de présélection
description: Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bee0522ea244cab2f5d6864b2a763df6e314e02d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805152"
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