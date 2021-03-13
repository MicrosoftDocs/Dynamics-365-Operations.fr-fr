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
ms.openlocfilehash: f291e28584dadc465092d99a1354fda793ff7560
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126144"
---
# <a name="screening-frequency-generate-from"></a>Date de début pour le calcul de la fréquence de présélection

Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmfrequencygeneratefrom

Cette énumération fournit le jeu d'options de valeurs pour déterminer la date de début du calcul pour la prochaine présélection obligatoire.

| Valeur  | Étiquette | Description  |
| --- | --- | --- |
| 200000000 Non sélectionné | Aucune valeur n'a été sélectionnée. |
| 200000001 Date de fin | Le calcul est effectué à partir de la dernière date des tests. |
| 200000002 Date obligatoire | Le calcul est effectué à partir de la dernière date des tests obligatoires. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l'entité Candidat à l'embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
