---
title: Date de début pour le calcul de la fréquence de présélection
description: Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 238cd5da750d815c904090cc9002e3d1a5d2bcc7
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464572"
---
# <a name="screening-frequency-generate-from"></a>Date de début pour le calcul de la fréquence de présélection

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmfrequencygeneratefrom

Cette énumération fournit le jeu d’options de valeurs pour déterminer la date de début du calcul pour la prochaine présélection obligatoire.

| Valeur  | Étiquette | Description  |
| --- | --- | --- |
| 200000000 Non sélectionné | Aucune valeur n’a été sélectionnée. |
| 200000001 Date de fin | Le calcul est effectué à partir de la dernière date des tests. |
| 200000002 Date obligatoire | Le calcul est effectué à partir de la dernière date des tests obligatoires. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]