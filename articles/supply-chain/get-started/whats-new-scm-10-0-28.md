---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.28 (août 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.28.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 2b129481399897337e960ec2d708d69a563b5435
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902051"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10028-august-2022"></a>Version préliminaire de Dynamics 365 Supply Chain Management 10.0.28 (août 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version préliminaire 10.0.28. Cette version a un numéro de build de 10.0.1264 et est disponible selon le programme suivant :

- **Version préliminaire de la version :** mai 2022
- **Disponibilité générale de la version (mise à jour automatique) :** juillet 2022
- **Disponibilité générale de la version (mise à jour automatique) :** juillet 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Inventaire et logistique | [Entités d’intégration des coûts au débarquement pour les transitaires tiers](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Vue d’ensemble des entités de coût au débarquement](../landed-cost/landed-cost-entities-overview.md) | Activé par défaut |
| Planification | [Planification des besoins en matériaux basée sur la demande (DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | Bientôt disponible | Gestion des fonctions :<br>*(Version préliminaire) DDMRP pour Optimisation de la planification* |
| Planification | [Prise en charge de l'optimisation de la planification pour la logique capable-to-promise (CTP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capable-to-promise-ctp) | Bientôt disponible | Gestion des fonctions :<br>*(Version préliminaire) CTP pour Optimisation de la planification* |
| Planification | [Prise en charge de l’optimisation de la planification pour la durée de conservation](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Bientôt disponible | Activé par défaut |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Gestion des entrepôts et des stocks | Activer la disponibilité intersociétés pour n’afficher que la quantité disponible non nulle | Cette fonction vous permet de choisir si les articles avec une quantité en stock nulle doivent être inclus dans la liste en stock intersociétés. Vous pouvez contrôler cette option à l’aide du paramètre **Ne pas afficher les articles avec une quantité en stock nulle dans la liste en stock intersociétés**, que cette fonctionnalité ajoute à la page **Paramètres de gestion des stocks et des entrepôts**. |
| Gestion des entrepôts et des stocks | (Inde) Pour les règles de prix de transfert, ignorer l’emplacement lorsque « Code entrepôt d’origine » est défini sur « Tout » | <p>Cette fonctionnalité s’applique uniquement aux localisations en Inde. Cela rend le processus de configuration des prix de transfert pour les articles en transfert de stock plus intuitif.</p><p>Vous paramétrez les prix de transfert en configurant chaque article avec des règles de prix de transfert. Une façon de faire cette configuration est d’inclure une ligne de règle où le champ **Du code d’entrepôt** est défini sur *Tout*. Ce paramètre indique que le prix de transfert défini par la ligne doit s’appliquer quel que soit l’entrepôt dans lequel l’article est prélevé. Lorsque cette fonction est activée, les règles de prix de transfert où le champ **Du code d’entrepôt** est défini sur *Tout* ignorera le paramètre **Emplacement**. Par conséquent, la règle s’appliquera quel que soit l’emplacement spécifié sur l’ordre de transfert. Ce comportement est probablement ce qui est attendu, car l’emplacement se situe sous l’entrepôt dans la hiérarchie de la dimension de stockage.</p><p>Sans cette fonctionnalité, le système appliquera les règles de ce type uniquement lorsque l’emplacement sur l’ordre de transfert correspond exactement à l’emplacement défini pour la règle. (Si un emplacement vide est défini pour la règle, le système appliquera la règle uniquement aux ordres de transfert qui ont également une valeur vide pour l’emplacement.)</p> |
| Gestion des entrepôts et des stocks | Nettoyage des données de l’état de disponibilité du stock | Cette fonction fournit un moyen de nettoyer les données permettant de créer les états *Stockage des états sur le stock disponible*. |
| Contrôle de la production | Affecter les activités du projet pour l’accord de service et les lignes de commande de service | Cette fonctionnalité ajoute un champ nommé **Activité de projet** aux lignes de contrat de service et de commande de service, afin que vous puissiez définir une activité de projet pour eux. Cette fonctionnalité permet d’éviter les erreurs bloquantes lorsque vous publiez des journaux de projet de gestion des services qui nécessitent la définition d’une activité de projet.  |
| Gestion des entrepôts | Service de prélèvement de ligne de transfert manuel pour les administrateurs ou les utilisateurs approuvés similaires | Cette fonctionnalité permet aux administrateurs de sélectionner manuellement les transactions de stock liées aux lignes de transfert. Ces lignes incluent les lignes ayant déjà été libérées dans l’entrepôt. Les administrateurs ne doivent effectuer cette sélection que dans des cas exceptionnels, par exemple lorsque le système est dans un état corrompu. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les articles d'aide suivants. Ces articles ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans les sections précédentes. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Articles nouveaux ou mis à jour |
|---|---|
| Gestion des coûts | [Prix fixe de réception](../cost-management/fixed-receipt-price.md) |
| Gestion des coûts | [Foire aux questions sur le coût des stocks](../cost-management/inventory-costing-faq.md) |
| Gestion des coûts | [Principe de comptabilisation des comptes imputés](../cost-management/post-to-charge-account-accounting-principle.md) |
| Gestion des stocks | [Détails des transactions de stock](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.28 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications Finances and Operations, version 10.0.28 (juin 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.28, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

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
