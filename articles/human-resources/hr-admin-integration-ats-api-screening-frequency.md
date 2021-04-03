---
title: Fréquence de présélection
description: Cette rubrique décrit l’option Fréquence de présélection définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 4ad81fba659a5bb22ab5131519036e156a43a486
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464548"
---
# <a name="screening-frequency"></a>Fréquence de présélection

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Fréquence de présélection définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmfrequencyunit

Cette énumération fournit le jeu d’options des valeurs pour la fréquence de présélection. 

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 Occasionnelle uniquement | La présélection n’est requise qu’une seule fois. |
| 200000001 Quotidienne | La fréquence de présélection est calculée en jours. |
| 200000002 Hebdomadaire | La fréquence de présélection est calculée en semaines. |
| 200000003 Mensuelle | La fréquence de présélection est calculée en mois. |
| 200000004 Annuelle | La fréquence de présélection est calculée en années. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]