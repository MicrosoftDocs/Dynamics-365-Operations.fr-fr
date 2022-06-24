---
title: Processus de publication de l’optimisation de la planification et historique des versions
description: Cet article fournit des informations sur le processus de publication et l’historique des versions de l’optimisation de la planification.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 45a35eb32cb9e51d9f63f6687808fb511f894887
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873722"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Processus de publication de l’optimisation de la planification et historique des versions

[!include [banner](../../includes/banner.md)]

Microsoft met à jour l’optimisation de la planification sur une base mensuelle. Cependant, en fonction des besoins de l’entreprise, nous publions occasionnellement des mises à jour supplémentaires entre les versions planifiées.

Chaque version est publiée dans les régions individuelles où l’optimisation de la planification est disponible. Le processus prend généralement trois jours.

Pendant la mise à jour de l’optimisation de la planification, la planification générale peut s’exécuter un peu plus lentement que d’habitude.

Les environnements qui utilisent l’optimisation de la planification reçoivent automatiquement la dernière version. Aucune action de l’utilisateur n’est requise : le service est automatiquement mis à jour. Cependant, aucune fonctionnalité de changement radical n’est jamais automatiquement poussée vers les environnements. Par défaut, toutes les modifications considérées comme des ruptures sont désactivées et doivent être explicitement activées à l’aide de la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Par conséquent, ces modifications n’apparaîtront pas dans les environnements tant que vous n’aurez pas choisi de les activer.

Étant donné que les notifications ne s’affichent pas lorsque l’optimisation de la planification est mis à jour dans votre environnement, vous pouvez consulter les notes de publication dans le tableau suivant pour déterminer quand les modifications ont été publiées et quelles fonctionnalités elles ont introduites. Ce tableau indique les modifications qui ont été publiées pour l’optimisation de la planification, si ces modifications sont associées à une fonctionnalité de la gestion des fonctionnalités et la date de la publication.

| Modifications | Détails de la gestion des fonctionnalités | Dates de parution |
|---|---|---|
| <p>Améliorations générales des performances, de la qualité et de la stabilité.<p>[Maintenance du calendrier centralisé de l’optimisation de la planification](../supply-chain-calendars-master-planning.md)<p>[Suggestions d’optimisation de la planification pour optimiser l’offre existante](../action-messages.md)<p>[Prise en charge de l’optimisation de la planification pour la sous-traitance](../../production-control/manage-subcontract-work-production.md) | Aucune gestion des fonctionnalités n’est requise. | 7-11 mars 2022 |
| <p>Ajout de la prise en charge de la priorité de planification pour les ordres de fabrication. | Disponible avec la version 10.0.25 dans le cadre de la fonctionnalité *Support MRP piloté par la priorité pour l’optimisation de la planification*. | 12-18 novembre 2021 |
| <p>Améliorations générales des performances, de la qualité et de la stabilité. | Aucune gestion des fonctionnalités n’est requise. | 12-18 novembre 2021 |
| <p>Ajout de la prise en charge des formules de calcul du temps de traitement, de l’itinéraire de production avec chevauchement et du numéro d’opération de production sur les transactions de besoins.</p><p>Messages d’erreur améliorés pour la planification de la production liés au délai d’attente, à la capacité introuvable et à l’itinéraire cyclique.</p><p>Amélioration de la cohérence lors du calcul des dates de réception et de sortie des commandes planifiées et des commandes confirmées.</p><p>Améliorations générales des performances, de la qualité et de la stabilité. | Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification* | 22 au 27 octobre 2021 |
| <p>Ajout de la prise en charge de la prise en compte du pourcentage de rebut dans le calcul du temps de traitement.</p><p>Ajout de la prise en charge du numéro d’opération et de l’utilisation des matériaux lors de la planification. | Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification* | 5 au 7 octobre 2021 |
| <p>Ajout de la prise en charge des types de tâches de routage de production : **File d’attente avant**, **File d’attente après**, et **Temps de transport**.</p><p>Améliorations générales des performances, de la qualité et de la stabilité. | Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification* | 25 au 30 septembre 2021 |
| <p>Ajout de la prise en charge des plans de versions avec **Méthode de planification** défini sur *Planification des opérations*.</p><p>Sur la page **Groupes d’itinéraires**, respectez les paramètres des cases **Activation**, **Temps de travail** et **Capacité** pour les lignes avec un **Itinéraire/type de tâche** défini sur *Configurer* ou *Traiter*. </p><p>Améliorations générales des performances, de la qualité et de la stabilité. | <p>La planification des opérations est disponible dans la gestion des fonctionnalités à partir de la version 10.0.20.</p><p>Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification*</p>  | 9-17 septembre 2021 |
| Améliorations générales des performances, de la qualité et de la stabilité. | Aucune gestion des fonctionnalités n’est requise. | 25–30 août 2021 |
| <p>Champ **Délai** ajouté aux ordres planifiés.</p><p>Améliorations générales des performances, de la qualité et de la stabilité.</p> | Aucune gestion des fonctionnalités n’est requise. | 12–17 août 2021 |
| <p>Exigences de type de ressource ajoutées pour la planification de capacité infinie.</p><p>Efficacité des ressources et efficacité du calendrier améliorées pour une planification de capacité infinie.</p><p>Pour plus d’informations, voir [Planification avec une capacité infinie](infinite-capacity-planning.md). | <p>Disponible dans la gestion des fonctionnalités à partir de la version 10.0.20.</p><p>Nom de la fonctionnalité : *Planification des capacités infinies pour l’optimisation de la planification*</p> | 6–12 juillet 2021 |
| Améliorations générales de la qualité. | Aucune gestion des fonctionnalités n’est requise. | 6–12 juillet 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
