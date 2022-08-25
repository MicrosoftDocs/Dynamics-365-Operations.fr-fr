---
title: Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.26 (mai 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.26.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: b44b044bf10115a7fcaf347a3b6f1759c2a68cb6
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219062"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.26 (mai 2022)

[!include [banner](../includes/banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.26. Cette version a un numéro de build de 10.0.1192 et est disponible comme suit :

- **Version préliminaire :** Mars 2022
- **Disponibilité générale de la version (auto-mise à jour) :** Avril 2022
- **Disponibilité générale de la version (auto-mise à jour) :** Avril 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités qui auront été intégrées à la version après la publication initiale de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Inventaire et logistique | [Requête de disponibilité de la visibilité de l’inventaire pour prendre en charge les éléments de gestion des entrepôts avancés](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Prise en charge de la Visibilité des stocks pour les articles WMS](../inventory/inventory-visibility-whs-support.md) | Gestion des fonctions :<br>*Activer les articles d’entrepôt dans Visibilité des stocks* |
| Inventaire et logistique | [Disponible à la promesse pour le complément Visibilité des stocks](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [Plannings de changement du stock disponible et disponibilité à la vente de la Visibilité des stocks](../inventory/inventory-visibility-available-to-promise.md) | Activé par la configuration du service |
| Fabrication | [Éléments à poids variable pour l’interface d’exécution de l’atelier de production](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [Comment les travailleurs utilisent l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-use.md) | Gestion des fonctions :<br>*État sur les articles en poids variable à partir de l’interface d’exécution de l’atelier de production* |
| Fabrication | Onglet Mes tâches sur l’interface d’exécution de l’atelier de production <!-- KFM: Add link to release plan when available --> | [Comment les travailleurs utilisent l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-use.md) | Gestion des fonctions :<br>*Onglet Mes tâches sur l’interface d’exécution de l’atelier de production* |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Approvisionnements | Valider les quantités enregistrées de produits stockés et les restes de produits non stockés pour les réceptions et les factures fournisseur | Cette fonctionnalité modifie la manière dont les quantités de produits non stockés (tels que les services) sont validées au moment du traitement des factures fournisseur et des expéditions entrantes par rapport aux bons de commande. La fonctionnalité modifie le comportement de l’option de quantité *Quantité enregistrée et services* pour la validation des reçus et des factures fournisseur en la modifiant pour correspondre au comportement de l’option *Quantité enregistrée et produits non stockés* déjà fournie au moment de la validation des quantités pour les bons de livraison des ventes.<br><br>Quand vous validez un accusé de réception de marchandises ou une facture fournisseur à l’aide de l’option de quantité *Quantité enregistrée et services*, le système valide la quantité enregistrée de produits stockés, mais valide la quantité restante de produits non stockés (dont les services et les non-services). Sans cette fonction, le système continue de valider la quantité enregistrée de produits stockés (dont les services configurés en tant qu’articles en stock), mais valide toujours la quantité commandée totale de produits de service non stockés (et ignore les produits non stockés qui n’appartiennent pas au type *Service*). |
| Approvisionnements | Synchroniser les dimensions de suivi sur les lignes de commandes fournisseur et commandes client intersociétés | Cette fonctionnalité vous permet de contrôler si les dimensions de suivi des numéros de série et de lot sont synchronisées sur les ventes intersociétés et les lignes de commande fournisseur. Elle ajoute de nouveaux paramètres aux deux onglets **Politiques de bons de commande** et **Politiques de commandes client** de la page de configuration **Intersociétés** pour les clients et les fournisseurs. Elle met également à jour les noms de quelques paramètres connexes à proximité pour plus de clarté.<br><br>Si vous utilisez les processus de gestion des entrepôts (WMS), sachez que cette fonctionnalité ne synchronisera uniquement les numéros de série et de lot quand ces dimensions se situent au-dessus de l’emplacement dans la hiérarchie de réservation de la destination cible. |
| Gestion des informations sur les produits | Nettoyer les valeurs de l’attribut de produit | Cette fonction ajoute une tâche périodique appelée **Nettoyer les valeurs de l’attribut de produit**, qui nettoie les enregistrements de valeur de l’attribut de produit qui ne sont plus associés à un produit via une catégorie de produit. |
| Gestion des entrepôts et des stocks | (Russie) Empêcher les écarts au moment de l’émission des GTD pour les commandes fournisseur qui incluent des articles activés par le service de gestion du flux de travail | Cette fonctionnalité n’est disponible que pour la Russie. Elle évite les écarts qui se produisent au moment de l’émission de numéros de déclaration en douane (GTD) russes pour les bons de commande d’importation qui incluent des éléments activés pour les processus de gestion des entrepôts (WMS). Le processus d’émission GTD modifie certaines valeurs de dimension de stock sur les transactions de stock associées pour les factures incluses dans le journal personnalisé, ce qui entraîne des écarts entre les enregistrements de travail pour le bon de commande et les transactions de stock pour l’achat. Quand cette fonctionnalité est activée, le processus d’émission de GTD génère un travail d’ajustement qui élimine ces écarts. |
| Gestion des entrepôts | Analyseur amélioré pour les codes-barres GS1 | Cette fonctionnalité ajoute un analyseur amélioré pour les données de symboles GS1. Le nouvel analyseur implémente l’algorithme de spécification générale GS1 pour l’analyse des symboles GS1 et fournit une validation des données plus solide. Pour plus d’informations, voir [Lecture des codes-barres GS1](../warehousing/gs1-barcodes.md). |
| Gestion des entrepôts | Nouvelles pages de l’atelier de planification des chargements | Ajoute deux nouvelles pages de l’atelier de planification des chargements : **Atelier de planification des chargements entrants** et **Atelier de planification des chargements sortants**. |
| Gestion des entrepôts | Application Warehouse Management - GTD vierge | Cette fonctionnalité n’est disponible que pour la Russie. Il permet aux collaborateurs utilisant l’application mobile Warehouse Management de laisser les numéros de déclaration en douane (GTD) russes vides en cas de besoin. Si la dimension de suivi GTD est configurée pour autoriser les valeurs vides, le système acceptera les valeurs vides pour GTD pour les opérations de stock à condition que le stock disponible soit disponible. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les articles d'aide suivants. Ces articles ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans les sections précédentes. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Articles nouveaux ou mis à jour |
|---|---|
| Gestion des coûts | Des exemples et des diagrammes mis à jour ont été ajoutés à chacun des articles suivants :<ul><li>[FIFO avec valeur physique et marquage](../cost-management/fifo-physical-value-marking.md)</li><li>[LIFO avec valeur physique et marquage](../cost-management/lifo-physical-value-marking.md)</li><li>[Date LIFO avec valeur physique et marquage](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Prix de revient moyen en cours](../cost-management/running-average-cost-price.md)</li><li>[Moyenne pondérée avec valeur physique et marquage](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.26 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.26 (mai 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.26, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 et les clouds du secteur : plan de la 1e vague de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 1e vague de lancement 2022](/dynamics365-release-plan/2022wave1/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

L'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

