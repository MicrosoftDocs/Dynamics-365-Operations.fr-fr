---
title: Processus de publication de l’optimisation de la planification et historique des versions
description: Cette rubrique fournit des informations sur le processus de publication et l’historique des versions de l’optimisation de la planification.
author: crytt
ms.date: 7/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 64c8cd3ed6ff522a9ef90831ae502c5d50fbc05816aaa764d2a8e122934fc2bb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722389"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Processus de publication de l’optimisation de la planification et historique des versions

[!include [banner](../../includes/banner.md)]

Microsoft met à jour l’optimisation de la planification sur une base mensuelle. Cependant, en fonction des besoins de l’entreprise, nous publions occasionnellement des mises à jour supplémentaires entre les versions planifiées.

Chaque version est publiée dans les régions individuelles où l’optimisation de la planification est disponible. Le processus prend généralement trois jours.

Pendant la mise à jour de l’optimisation de la planification, la planification générale peut s’exécuter un peu plus lentement que d’habitude.

Les environnements qui utilisent l’optimisation de la planification reçoivent automatiquement la dernière version. Aucune action de l’utilisateur n’est requise : le service est automatiquement mis à jour. Cependant, aucune fonctionnalité de changement radical n’est jamais automatiquement poussée vers les environnements. Par défaut, toutes les modifications considérées comme des ruptures sont désactivées et doivent être explicitement activées à l’aide de la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Par conséquent, ces modifications n’apparaîtront pas dans les environnements tant que vous n’aurez pas choisi de les activer.

Étant donné que les notifications ne s’affichent pas lorsque l’optimisation de la planification est mis à jour dans votre environnement, vous pouvez consulter les notes de publication dans le tableau suivant pour déterminer quand les modifications ont été publiées et quelles fonctionnalités elles ont introduites. Ce tableau indique les modifications qui ont été publiées pour l’optimisation de la planification, si ces modifications sont associées à une fonctionnalité de la gestion des fonctionnalités et la date de la publication.

| Modifications | Détails de la gestion des fonctionnalités | Date de sortie |
|---|---|---|
| <p>Exigences de type de ressource pour la planification de capacité infinie</p><p>Efficacité des ressources et efficacité du calendrier pour une planification de capacité infinie</p><p>Pour plus d’informations, voir [Planification avec une capacité infinie](infinite-capacity-planning.md). | <p>Disponible dans la gestion des fonctionnalités à partir de la version 10.0.20.</p><p>Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification*</p> | 6 juillet 2021 |
| Améliorations générales de la qualité | Aucune gestion des fonctionnalités n’est requise. | 6 juillet 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
