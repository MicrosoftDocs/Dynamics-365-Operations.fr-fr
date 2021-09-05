---
title: Processus de publication de l’optimisation de la planification et historique des versions
description: Cette rubrique fournit des informations sur le processus de publication et l’historique des versions de l’optimisation de la planification.
author: crytt
ms.date: 8/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fcd18341629afcf3092a457ae711e27b0bbfeb2a
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394412"
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
| <p>Champ **Délai** ajouté aux ordres planifiés.</p><p>Améliorations générales des performances, de la qualité et de la stabilité.</p> | Aucune gestion des fonctionnalités n’est requise. | 16 août 2021 |
| <p>Exigences de type de ressource ajoutées pour la planification de capacité infinie.</p><p>Efficacité des ressources et efficacité du calendrier améliorées pour une planification de capacité infinie.</p><p>Pour plus d’informations, voir [Planification avec une capacité infinie](infinite-capacity-planning.md). | <p>Disponible dans la gestion des fonctionnalités à partir de la version 10.0.20.</p><p>Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification*</p> | 6 juillet 2021 |
| Améliorations générales de la qualité. | Aucune gestion des fonctionnalités n’est requise. | 6 juillet 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
