---
title: Statut de la demande de recrutement
description: Cette rubrique décrit l’option Statut de la demande de recrutement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: d845179077fc2e04dfb3bd05eaa70b0a2a016121
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067099"
---
# <a name="recruiting-request-status"></a>Statut de la demande de recrutement


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Statut de la demande de recrutement définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequeststatus

Cette énumération fournit le jeu d’options pour les valeurs de statut d’une demande de recrutement.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Brouillon | La demande est en projet et n’est pas prête pour le recrutement actif. |
| 200000001 | En cours de révision | La demande a été soumise et est acheminée pour approbation par le workflow. Uniquement disponible lorsque le workflow est activé. |
| 200000002 | Facture en attente | La demande est en attente d’une action de workflow. Uniquement disponible lorsque le workflow est activé. |
| 200000003 | Annulée | La demande a été annulée. Uniquement disponible lorsque le workflow est activé. |
| 200000004 | Refusé | La demande a été refusée. Uniquement disponible lorsque le workflow est activé. |
| 200000005 | Actif.ve | Workflow quelconque terminé et approuvé, et demande prête pour un recrutement actif. |
| 200000006 | Clôturée(s) | La demande de recrutement est clôturée. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
