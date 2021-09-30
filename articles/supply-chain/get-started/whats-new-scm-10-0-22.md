---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.22 (novembre 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c4aac62b36cd271e1c5fc3bcbbfdd785963fc368
ms.sourcegitcommit: 24e20b3b96834b23311f1bf5dbab28baf3323728
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7484070"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10022-november-2021"></a>Version préliminaire de Dynamics 365 Supply Chain Management 10.0.22 (novembre 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire de Microsoft Dynamics 365 Supply Chain Management 10.0.22. Cette version a un numéro de build de 10.0.995 et est disponible comme suit :

- **Version préliminaire :** septembre 2021
- **Disponibilité générale de la version (mise à jour automatique) :** octobre 2021
- **Disponibilité générale de la version (mise à jour automatique) :** novembre 2021

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. La colonne *Fonctionnalité* fournit des liens vers le [programme de publication](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), où vous pouvez voir les dates de lancement officiel de chaque fonctionnalité. La colonne *Plus d’informations* fournit plus de détails et/ou de liens vers la documentation connexe. Pour déterminer comment activer une fonctionnalité, voir la colonne *Activé par*. Pour plus d’informations sur la gestion des fonctionnalités, voir [Présentation de la gestion des fonctions](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Il se peut que nous mettions à jour de cette rubrique pour inclure des fonctionnalités qui auront été intégrées à la version après la publication initiale de cette rubrique.

| Fonctionnalités | Fonctionnalité | Informations supplémentaires | Activé par   |
|---|---|---|---|
| Planification | [Prise en charge de l’optimisation de la planification pour l’allocation des ressources en fonction des capacités](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Planification avec sélection des ressources en fonction des capacités](../master-planning/planning-optimization/capability-based-scheduling.md) | Gestion des fonctionnalités (*Planification des capacités infinies pour l’optimisation de la planification*) |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire). Si vous souhaitez utiliser l’une de ces fonctionnalités, vous devez l’activer explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Fonctionnalités | Nom de la fonction dans la Gestion des fonctionnalités | Informations supplémentaires |
|---|---|---|
| Gestion des coûts | Créer des documents associés pour les réévaluations d’arrondi des coûts standard | <p>Lorsqu’une écriture financière d’inventaire (telle qu’une facture de commande client ou une transaction d’inventaire) est effectuée, cette fonction oblige le système à créer un document distinct pour toutes les réévaluations d’arrondi des coûts standard associées et à le joindre à la pièce comptable d’écriture financière en tant que pièce associée.</p><p>Sans cette fonctionnalité, le système enregistre les réévaluations d’arrondi des coûts standard sur le même enregistrement de document. Ce comportement peut parfois entraîner des informations de date contradictoires, car les réévaluations utilisent la date de la session ou du système, alors que les écritures financières utilisent la date comptable.</p> |
| Topologie hybride distribuée | *(Aucune gestion des fonctionnalités n’est requise.)* | <p>Cette version étend les capacités de planification de la charge sortante de la charge de travail de gestion d’entrepôt pour les unités à l’échelle Cloud et périphérie.</p><p>Pour plus d’informations, voir [Charges de travail de gestion des entrepôts pour les unités d’échelle cloud et de périphérie](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Gestion des modifications d’ingénierie | Générer des variantes pour les produits d’ingénierie | <p>Cette fonctionnalité vous permet de générer plusieurs variantes pour un produit d’ingénierie, en fonction de sa couleur, sa taille, son style ou ses dimensions de configuration.</p><p>Pour plus d’informations, voir [Générer des variantes pour les produits d’ingénierie](../engineering-change-management/engineering-variants.md).</p> |
| Gestion des entrepôts et des stocks | Intégration de la visibilité du stock avec la compensation de réservation | <p>Cette fonction ne peut être activée qu’une fois la fonctionnalité *Intégration de la visibilité de l’inventaire* activée. Il fournit des fonctionnalités pour compenser les réservations effectuées sur la visibilité du stock.</p><p>Pour plus d’informations, voir [Réservation dans la visibilité des stocks](../inventory/inventory-visibility-reservations.md).</p> |
| Ventes et marketing | Limiter le nombre de commandes clients qui peuvent être sélectionnées pour validation | <p>Cette fonctionnalité est activée automatiquement. Elle ajoute un champ appelé **Nombre max. de commandes client à valider** dans la page **Paramètres de la comptabilité client**. Ce champ vous permet de définir le nombre maximal de commandes client pouvant être sélectionnées lors de la validation des confirmations, des prélèvements, des bons de livraison et des factures à partir de la page de liste des commandes client. La valeur par défaut est *100*.</p><p>Cette fonctionnalité permet d’améliorer les performances de la page de liste des commandes client lorsqu’un nombre important de commandes client est sélectionné. Elle n’a aucun impact sur le nombre de commandes client pouvant être traitées par une tâche périodique.</p> |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les rubriques d’aide suivantes. Ces rubriques ne sont pas nécessairement liées aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans la section précédente. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Rubriques nouvelles ou mises à jour |
|---|---|
| Gestion des modifications d’ingénierie | La [vue d’ensemble de la gestion des modifications d’ingénierie](../engineering-change-management/product-engineering-overview.md) répertorie désormais toutes les fonctionnalités optionnelles connexes disponibles dans la gestion des fonctionnalités. |
| Planification générale | [Paramétrage de la prévision de la demande](../master-planning/demand-forecasting-setup.md) |
| Planification générale | [Exigences nettes et informations de rattachement avec l’optimisation de la planification](../master-planning/planning-optimization/net-requirements.md) |
| Gestion des entrepôts | [Libération dans l’entrepôt](../warehousing/release-to-warehouse-process.md) fournit un aperçu détaillé du processus complet de libération en entrepôt |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.22 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.22 des applications Finance and Operations (novembre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md). <!-- KFM: Confirm link -->

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.22, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2021

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2021](/dynamics365-release-plan/2021wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

La rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans la rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]