---
title: Fréquence de présélection
description: Cette rubrique décrit l’option Fréquence de présélection définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: e6e0636c48c867f88918decc31e00fda8cf844e1f6a356f76a1b0e706a946b58
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718153"
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