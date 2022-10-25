---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.30 (novembre 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.30.
author: kamaybac
ms.date: 09/08/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 18fec49f2388159cae0809c63685102a04e90c57
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689184"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10030-november-2022"></a>Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.30 (novembre 2022)

[!include [banner](../includes/banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.30. Cette version a un numéro de build de 10.0.1362 et est disponible selon le programme suivant :

- **Version préliminaire :** septembre 2022
- **Disponibilité générale de la version (mise à jour automatique) :** octobre 2022
- **Disponibilité générale de la version (mise à jour automatique) :** novembre 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Fabrication | [Surveiller l’équipement avec Sensor Data Intelligence](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Page d’accueil de Sensor Data Intelligence](../sensor-data-intelligence/sdi-home-page.md) | Gestion des fonctions :<br>*(Version préliminaire) Sensor Data Intelligence* |
| Gestion des entrepôts | [Détours à plusieurs niveaux pour l’application mobile Warehouse Management](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/multi-level-detours-warehouse-management-mobile-app) | [Configurer des détours pour les étapes dans les éléments de menu de l’appareil mobile](../warehousing/warehouse-app-detours.md) | Gestion des fonctions :<br>*Détours à plusieurs niveaux pour l’application mobile Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Contrôle de la production | Informations disponibles sur la page des ordres de fabrication à publier | Ajoute une colonne pour la quantité de stock disponible sur la ligne dans la section Lignes de la page **Ordres de production à libérer**. |
| Gestion du transport | Affecter des expéditions aux segments de route liés | Cette fonctionnalité permet au système de répartir les coûts de fret d’expédition avec plus de précision, y compris pour les chargements avec plusieurs expéditions livrées vers différentes destinations de segment le long d’un seul itinéraire. Il attribue à chaque envoi le segment d’itinéraire le plus approprié en fonction des adresses de destination de l’envoi et du segment. La fonctionnalité calcule ensuite le coût de transport de chaque expédition en tant que proportion du coût de transport total du chargement, en fonction du poids, du volume, de la quantité et de la distance parcourue relatifs à l’expédition. Cette fonctionnalité s’applique uniquement aux expéditions gérées à l’aide du module de gestion du transport (TMS). |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.30 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications Finances et Opérations, version 10.0.30 (novembre 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de la version 10.0.29, connectez-vous à Lifecycle Services (LCS) et consultez l’ [Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 et les clouds du secteur : plan de la 1e vague de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2022](/dynamics365-release-plan/2022wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

L'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
