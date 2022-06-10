---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.27 (juillet 2022)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.27.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 77c79c88b08844bf7e399a762bb9eb9746ffb71a
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2022
ms.locfileid: "8812942"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10027-july-2022"></a>Version préliminaire de Dynamics 365 Supply Chain Management 10.0.27 (juillet 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version préliminaire 10.0.27. Cette version a un numéro de build de 10.0.1227 et est disponible selon le programme suivant :

- **Version préliminaire :** avril 2022
- **Disponibilité générale de la version (mise à jour automatique) :** juin 2022
- **Disponibilité générale de la version (mise à jour automatique) :** juillet 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cette rubrique pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cette rubrique.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Inventaire et logistique | [Répartition de stock pour le complément Visibilité des stocks](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | [Répartition de stock pour Visibilité des stocks](../inventory/inventory-visibility-allocation.md) | Activé par défaut |
| Fabrication | Vue « Ma journée » pour l’interface d’exécution de l’atelier de production | [Comment les collaborateurs utilisent l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-use.md) et [Afficher les soldes de vacances dans l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-payroll-stats.md) | Gestion des fonctions :<br>*Vue « Ma journée » pour l’interface d’exécution de l’atelier de production* |
| Planification | [Prise en charge de l’optimisation de la planification pour la sous-traitance](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Gestion du travail de sous-traitance en production](../production-control/manage-subcontract-work-production.md) | Activé par défaut |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Planification générale | Tenir compte du délai d’inventaire au moment de la création d’un ordre de transfert planifié | À la création d’un ordre de transfert prévu, cette fonctionnalité entraîne le système à tenir compte du délai de stock indiqué dans les paramètres de commande par défaut de l’article au moment de la date de réception de l’ordre de transfert prévu où le contrôle de la date de livraison est configuré sur *Aucun* ou *Ventes*. Quand le délai de transfert est spécifié, sa valeur est utilisée pour le calcul de la date de réception et les jours de transport seront ignorés. |
| Approvisionnements | Informations de taxe du contrat de courtier par défaut sur les lignes de facture fournisseur | Cette fonctionnalité introduit une logique pour définir des valeurs par défaut pour les champs **Taxe de vente** et **Taxe de vente sur les articles** sur les lignes de facture fournisseur du contrat de courtage. Cette logique s’applique uniquement quand le type de frais sur la ligne de contrat du courtier est comptabilité/comptabilité. Le groupe de taxe de vente de l’article tirera sa valeur par défaut de la catégorie d’approvisionnement de courtage (si elle est configurée) ou du type de frais. Le groupe de taxe de vente tire sa valeur par défaut du compte fournisseur. |
| Approvisionnements | Limiter le nombre de lignes des commandes fournisseur par tâche de traitement par lots | Cette fonctionnalité vous aide à optimiser les performances système à la validation des confirmations et des accusés de réception de marchandises. Il ajoute un nouveau paramètre nommé **Lignes par tâche** à l’onglet **Livraison** de la page **Paramètres d’approvisionnement et d’approvisionnement**. Ce nouveau paramètre vous permet de limiter le nombre de lignes de la commande fournisseur que chaque tâche de traitement par lots traite. Par conséquent, cela peut aider à empêcher les tâches de traitement par lots volumineuses de ralentir le système. |
| Gestion des informations sur les produits | Compléter les valeurs d’attribut de produit | Cette fonctionnalité ajoute une tâche périodique nommée *Remplir les valeurs d’attribut de produit*. Cette nouvelle tâche périodique crée des enregistrements de valeur de l’attribut de produit manquants pour les attributs associés à des produits via une catégorie de produit. |
| Contrôle de la production | Configuration supplémentaire sur l’interface d’exécution de l’atelier de production | <p>Cette fonctionnalité ajoute les options suivantes à la page **Configurer l’exécution de l’atelier de production** :</p><ul><li>**Ouverture automatique de la boîte de dialogue à la fin d’une recherche** – Quand cette option est activée, la boîte de dialogue **Démarrer la tâche** s’ouvre automatiquement quand les collaborateurs utilisent la barre de recherche pour trouver une tâche.</li><li>**Ouverture automatique de la boîte de dialogue de progression de l’état** – Quand cette option est activée, la boîte de dialogue **Progression du rapport** pour la tâche s’ouvre automatiquement quand les collaborateurs utilisent la barre de recherche pour trouver une tâche.</li><li>**Quantité restante par défaut dans la boîte de dialogue de progression du rapport** – Quand cette option est activée, la boîte de dialogue **Signaler les progrès** affiche la quantité restante à signaler sur un travail de production.</li></ul><p>Pour plus d’informations, consultez [Configurer l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md).</p> |
| Contrôle de la production | Équipes de production dans l’interface d’exécution de l’atelier de production | <p>Quand plusieurs collaborateurs sont affectés à la même tâche de production, ils peuvent désormais désigner un collaborateur comme pilote. Les collaborateurs restants deviennent automatiquement les assistants de ce pilote. Pour l’équipe en résultant, seul le pilote doit enregistrer le statut de la tâche, tandis que les enregistrements de temps s’appliquent à tous les membres de l’équipe. Cette fonctionnalité prend également en charge un scénario nommé *ressource d’assistance*. Dans ce scénario, un collaborateur peut s’inscrire en tant qu’assistant d’un autre collaborateur, qui devient alors le pilote du groupe nouvellement formé.</p><p>Pour plus d’informations, consultez [Utilisation de l’interface d’exécution de l’atelier de production par les collaborateurs](../production-control/production-floor-execution-use.md).</p> |
| Contrôle de la production | Générer un état sur les éléments de planification dans l’interface d’exécution à l’atelier de production | Cette fonctionnalité simplifie le processus de création de rapports sur les commandes de traitement par lots pour les articles de planification dans l’interface d’exécution de l’atelier de production. Quand une commande de traitement par lots est créée pour un produit dont le type de production est *Article de planification*, le signalement comme terminé ne peut être fait que sur les coproduits et les sous-produits pour cette commande groupée. Les commandes par lots pour les articles de planification sont généralement utilisées pour prendre en charge les processus de désassemblage, où un produit de matière première est désassemblé en plusieurs produits distincts. Quand un collaborateur signale un lot de commandes pour un article de planification comme terminé, la boîte de dialogue **Signaler les progrès** affiche désormais uniquement les coproduits et les sous-produits. Auparavant, il affichait également l’élément de planification, et ce comportement pouvait dérouter les collaborateurs. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les rubriques Aide suivantes. Ces rubriques ne sont pas nécessairement liées aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans les sections précédentes. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Rubriques nouvelles ou mises à jour |
|---|---|
| Gestion des coûts | [Date de moyenne pondérée avec Inclure valeur physique et marquage](../cost-management/weighted-average-date.md) |
| Topologie hybride distribuée | [Essayer les unités d’échelle dans une topologie hybride distribuée](../cloud-edge/cloud-edge-try-out.md) |
| Double écriture | [Synchroniser à la demande avec le moteur de tarification de Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Gestion des entrepôts | [Lancement vers l’entrepôt](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance et Opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.27 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications Finances and Operations, version 10.0.27 (juin 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.27, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 et les clouds du secteur : plan de la 1e vague de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 1e vague de lancement 2022](/dynamics365-release-plan/2022wave1/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

La rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans la rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
