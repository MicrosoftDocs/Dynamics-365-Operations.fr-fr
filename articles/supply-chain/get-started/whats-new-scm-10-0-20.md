---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.20 (août 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Supply Chain Management 10.0.20.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3a35d3becbf81c51d29ef2e0f4cbf6a12cd196b8
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187624"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10020-august-2021"></a>Version préliminaire de Dynamics 365 Supply Chain Management 10.0.20 (août 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire de Microsoft Dynamics 365 Supply Chain Management 10.0.20. Cette version a un numéro de build de 10.0.886 et est disponible comme suit :

- **Version préliminaire de la version :** mai 2021
- **Disponibilité générale de la version (mise à jour automatique) :** juillet 2021
- **Disponibilité générale de la version (mise à jour automatique) :** juillet 2021


## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités comprises dans cette version. La colonne *Fonctionnalité* fournit des liens vers le [programme de publication](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), où vous pouvez voir les dates de lancement officiel de chaque fonctionnalité. La colonne *Plus d’informations* fournit plus de détails et/ou de liens vers la documentation connexe.

La plupart de ces fonctionnalités doivent être activées à l’aide de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) avant de pouvoir les utiliser. Certaines des fonctionnalités répertoriées sont toujours en version préliminaire, tandis que d’autres peuvent déjà être généralement disponibles.

| Fonctionnalités | Fonctionnalité | Informations supplémentaires |
|---|---|---|
| Inventaire et logistique | [Amélioration des performances des commandes client](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Cette fonctionnalité rend l’interface utilisateur plus réactive lors de l’ouverture de commandes client, en particulier les commandes comportant de nombreuses lignes. |
| Fabrication | [Invoquer les flux d’automatisation de processus pour créer des ordres de qualité](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Invoquer les flux d’automatisation de processus pour créer des ordres de qualité](../production-control/process-automation-quality-orders.md ) |
| Fabrication | [Interface d’exécution améliorée de l’atelier de production pour la fabrication](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [Configurer l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) |
| Gestion des informations sur les produits | [Gérer les changements de formules et de leurs composants](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Gérer les changements de formules et de leurs composants](../engineering-change-management/manage-formula-changes.md) |
| Gestion des informations sur les produits | [Vérifications de la disponibilité du produit](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Disponibilité du produit](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire). Si vous souhaitez utiliser l’une de ces fonctionnalités, vous devez l’activer explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Fonctionnalités | Nom de la fonctionnalité dans Gestion des fonctionnalités | Informations supplémentaires |
|---|---|---|
| Planification | Jours négatifs pour l’optimisation de la planification | Cette fonctionnalité en version préliminaire permet à l’optimisation de la planification de prendre en compte la tolérance de retard en fonction du paramètre **Jours négatifs** défini dans les groupes de couverture. |
| Planification | Autorisation parallèle de l’ajustement de la prévision de la demande | Cette fonctionnalité permet l’autorisation parallèle de la prévision de la demande ajustée dans la page **Prévision de la demande ajustée**. Cette fonctionnalité a pour but d’augmenter les performances lorsqu’un grand nombre de prévisions est autorisé. Lors de l’autorisation, l’utilisateur peut spécifier le **Nombre de fils de discussion** dans la boîte de dialogue d’autorisation. |
| Planification | (Aperçu) Confirmation et consolidation pouvant être traitées par lots pour les lots de commandes planifiées de consommables et d’articles emballés | Cette fonctionnalité vous permet d’utiliser les traitements par lots pour confirmer et consolider les commandes planifiées de consommables et d’articles emballés. |
| Contrôle de la production | Copier les gammes génériques | Cette fonctionnalité améliore la fonction de copie de la gamme pour permettre aux utilisateurs de copier des gammes qui ne sont pas spécifiques à un élément. Ellle permet au système de mettre à jour toutes les informations pertinentes (telles que le site, le groupe de gammes, les besoins en ressources et les différentes heures) une fois que la fonction de copie de la gamme a été utilisée pour remplacer une gamme qui n’est pas encore affectée à un article. |
| Contrôle de la production | Mettre à jour les ressources requises liées lorsqu’une opération de gamme est modifiée | Cette fonctionnalité permet au système de mettre à jour les ressources requises liées après qu’un utilisateur a modifié l’opération d’une étape de gamme existante. |
| Gestion des informations sur les produits | Pré-traitement du rapport de nomenclature pour éviter le délai d’attente | Cette fonctionnalité entraîne le prétraitement du rapport de nomenclature. Cela évitera les problèmes de délai d’attente lorsqu’il y a un chargement de données important pour le rapport. |
| Approvisionnements | Activer la réinitialisation des flux de travail liés à l’approvisionnement | Cette fonctionnalité en version préliminaire vous permet de réinitialiser les flux de travail suivants sur le statut brouillon : commande client, changement de fournisseur et demandes d’achat. |
| Gestion du transport | Activer la création d’un journal des factures fournisseur lorsqu’une facture des frais de transport est ignorée | Lorsque cette fonctionnalité est activée, un journal des factures fournisseur correspondant sera créé uniquement pour des raisons de rapprochement lorsque vous utilisez l’option de paiement du fournisseur. Sinon, le journal des factures sera toujours créé. |
| Gestion des entrepôts | Valider les modèles sélectionnés pour les tâches de réapprovisionnement | Cette fonctionnalité permet de s’assurer que les utilisateurs sélectionnent des modèles de réapprovisionnement valides lors de la configuration d’une tâche de réapprovisionnement. Elle empêche les utilisateurs de créer une tâche de réapprovisionnement sans modèle et de sélectionner des modèles de type *Demande de vague*, qui ne créera aucune tâche de réapprovisionnement et dont le traitement peut prendre beaucoup de temps. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les rubriques d’aide suivantes. Ils ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans la section précédente, mais ils peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Rubriques nouvelles ou mises à jour |
|---|---|
| Gestion des modifications d’ingénierie | [États et transactions du cycle de vie du produit](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Gestion des stocks | [Complément de visibilité de stock](../inventory/inventory-visibility.md)<br><br>[Vue d’ensemble de la gestion de la qualité et de la non-conformité](../inventory/quality-management-processes.md) (plus toutes les rubriques associées à la gestion de la qualité) |
| Approvisionnements | [Mettre à jour la certification des fournisseurs](../../finance/public-sector/manage-vendor-certification.md) |
| Contrôle de la production | [Appliquer un style à l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-styles.md) |
| Gestion des entrepôts | [Affecter des icônes et des titres d’étape pour l’application mobile Warehouse Management](../warehousing/step-icons-titles.md)<br><br>[Traitement différé du mouvement manuel des stocks](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.20 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.20 des applications Finance and Operations (juillet 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md). <!-- KFM: Confirm link -->

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.20, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365 : vague 1 du plan de publication 2021

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 : vague 1 du plan de publication 2021](/dynamics365-release-plan/2021wave1/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

La rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans la rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
