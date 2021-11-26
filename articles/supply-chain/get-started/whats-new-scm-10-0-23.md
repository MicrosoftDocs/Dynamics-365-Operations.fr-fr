---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.23
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.23.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 7950d225bd528c05c14df108f4d44cef3e348ebb
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777789"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10023"></a>Version préliminaire de Dynamics 365 Supply Chain Management 10.0.23

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire de Microsoft Dynamics 365 Supply Chain Management 10.0.23. Cette version a un numéro de build de 10.0.1037 et est disponible comme suit :

- **Version préliminaire de la version :** octobre 2021
- **Disponibilité générale de la version (mise à jour manuelle) :** décembre 2021

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. La colonne *Fonctionnalité* fournit des liens vers le [programme de publication](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), où vous pouvez voir les dates de lancement officiel de chaque fonctionnalité. La colonne *Plus d’informations* fournit plus de détails et/ou de liens vers la documentation connexe. Pour déterminer comment activer une fonctionnalité, voir la colonne *Activé par*. Pour plus d’informations sur la gestion des fonctionnalités, voir [Présentation de la gestion des fonctions](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Il se peut que nous mettions à jour de cette rubrique pour inclure des fonctionnalités qui auront été intégrées à la version après la publication initiale de cette rubrique.

| Fonctionnalités | Fonctionnalité | Informations supplémentaires | Activé par |
|---|---|---|---|
| Carnet d’adresses global | Définir un état/province par défaut pour chaque pays/région dans la configuration de l’adresse | Vous pouvez maintenant définir un état/province par défaut pour chaque pays/région dans la configuration d’adresse pour le carnet d’adresses global. Lorsqu’un état/province par défaut est défini, ce sera la valeur par défaut saisie dans les champs état/province lorsque vous créez un nouvel enregistrement de comté ou de ville pour ce pays/région. Voir également [Configuration de l’adresse](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Activé par défaut. |
| Inventaire&nbsp;et&nbsp;logistique | [Tâches de pause dans l’application mobile Warehouse Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Configurer des détours pour les étapes dans les éléments de menu de l’appareil mobile](../warehousing/warehouse-app-detours.md) | Gestion des fonctionnalités (*Détours de l’application Warehouse Management*) |
| Inventaire&nbsp;et&nbsp;logistique | [Champs promus de l’application Warehouse](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Configurer les champs promus pour les étapes dans l’appareil mobile](../warehousing/warehouse-app-promoted-fields.md)| Gestion des fonctionnalités (*Champs promus par l’application d’entrepôt*) |
| Fabrication | [Intégration des systèmes d’exécution de la production](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Intégration avec des systèmes d’exécution de fabrication tiers](../production-control/mes-integration.md) | Gestion des fonctionnalités (*Intégration du système d’exécution de la production*) |
| Fabrication | [État sur les co-produits et sous-produits de l’interface d’exécution de l’atelier de production](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [Comment les travailleurs utilisent l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-use.md) | Gestion des fonctionnalités (*État sur les co-produits et sous-produits de l’interface d’exécution de l’atelier de production*) |
| Planification | [Prise en charge de l’optimisation de la planification pour la planification basée sur les priorités](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Planification basée sur la priorité](../master-planning/planning-optimization/priority-based-planning.md) | Gestion des fonctionnalités (*Support MRP basé sur la priorité pour l’optimisation de la planification*) |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités qui sont nouvelles pour cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), où ils sont répertoriés en utilisant les noms indiqués dans la colonne *Nom de la fonctionnalité dans la gestion des fonctionnalités* qui figure dans le tableau suivant.

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Informations supplémentaires |
|---|---|---|
| Gestion des actifs | Comptes de contrepartie pour les dépenses dans les journaux des ordres de travail | Cette fonctionnalité vous permet de spécifier un compte de contrepartie pour chaque dépense répertoriée dans un journal des bons de travail. Vous pouvez généralement associer un compte fournisseur à chaque dépense, mais d’autres types de compte sont également pris en charge. Il ajoute deux nouvelles colonnes (**Type de compte de contrepartie** et **Compte de compensation**) au raccourci **Frais** de la page **Journal des ordres de travail**.|
| Gestion des coûts | Créer des justificatifs associés pour les réévaluations d’arrondi de coût standard | <p>Lorsqu’une écriture financière d’inventaire (telle qu’une facture de commande client ou une transaction d’inventaire) est effectuée, cette fonction oblige le système à créer un document distinct pour toutes les réévaluations d’arrondi des coûts standard associées et à le joindre à la pièce comptable d’écriture financière en tant que pièce associée.</p><p>Sans cette fonctionnalité, le système enregistre les réévaluations d’arrondi des coûts standard sur le même enregistrement de document. Ce comportement peut parfois entraîner des informations de date contradictoires, car les réévaluations utilisent la date de la session ou du système, alors que les écritures financières utilisent la date comptable.</p> |
| Gestion des entrepôts et des stocks | \[Russie\] Publier les transactions de stock financier Storno en fonction de l’indicateur de correction dans le justificatif financier pour les commandes clients | Cette fonctionnalité a un impact sur la fonctionnalité de correction des notes de crédit pour la Russie. Il permet la comptabilisation des transactions de stock pour les factures de vente conformément à l’option de correction dans le grand livre. Lorsque cette fonctionnalité est activée, il n’y a plus d’écarts entre l’indicateur **Correction** sur le justificatif financier de la transaction de stock et l’indicateur **Storno** sur les transactions de stock. |
| Gestion des entrepôts et des stocks | (Russie) Exécuter le calcul par lots de l’état de variation des stocks | Pour les emplacements russes de Supply Chain Management, cette fonction offre la possibilité d’exécuter par lots l’état de *variation des stocks*, de le stocker et d’afficher les états générés antérieurement. |
| Gestion des entrepôts et des stocks | (Russie) Utiliser les traductions dans la langue locale dans les écrans principaux spécifiques au pays ou à la région dans Gestion des stocks | Pour les localisations en russe de Supply Chain Management, cette fonctionnalité permet l’utilisation de traductions en russe pour les noms de produits/articles et les unités de mesure dans les impressions de stock spécifiques au russe suivantes : liste de comptage (INV-3), liste de comptage (INV-5), et Liste de comptage (INV-6). |
| Approvisionnements | Nettoyer l’historique des mises à jour des commandes fournisseur | Cette fonctionnalité vous permet de nettoyer les enregistrements historiques temporaires liés aux mises à jour des bons de commande. Il ajoute un nouveau bouton appelé **Nettoyer l’historique des mises à jour des achats** au volet Actions sur la page **Tous les bons de commande**. Cette fonctionnalité est activée par défaut. |
| Contrôle de la production | (Version préliminaire) Prélèvement automatique des matières activées pour les entrepôts pour les prélèvements automatiquement validés | Cette fonction vous permet de sélectionner automatiquement et de résoudre les dimensions de stock pour les journaux des prélèvements automatiquement validés, dérivés. |
| Contrôle de la production | Valider l’expiration des matières premières par rapport à la date de consommation prévue | Cette fonctionnalité modifie la manière dont les dates d’expiration des lots sont validées lors de la réservation d’un lot de matières premières à utiliser pendant la production. Lorsque cette fonctionnalité est activée, la date d’expiration du lot est validée par rapport à la date de consommation planifiée (la date de la matière première), telle qu’établie sur la ligne de nomenclature de production ou la ligne de formule de commande de lot. Lorsque cette fonctionnalité est désactivée, la date d’expiration du lot est validée par rapport à la date de livraison prévue de la production ou de la commande de lot (comme précédemment). |
| Ventes et marketing | Nettoyer l’historique des mises à jour de ventes selon l’âge | Cette fonctionnalité vous permet de définir l’âge maximum des enregistrements à conserver lors de l’exécution de la tâche périodique **Nettoyage de l’historique des mises à jour des ventes**. Les enregistrements plus anciens seront supprimés. Ceci est utile lorsque vous définissez la tâche pour qu’elle s’exécute périodiquement, car l’âge est toujours calculé par rapport à la date d’exécution de la tâche. Sans cette fonctionnalité, vous ne pouvez définir qu’une date spécifique pour les enregistrements les plus anciens à conserver. |
| Ventes et marketing | Améliorer les performances de l’état des « 100 principaux clients » | Cette fonction améliore les performances des rapports clients **Top 100** en exécutant toujours le rapport sur tous les clients (ce qui est son utilisation prévue) plutôt qu’en autorisant les requêtes personnalisées. Lorsque cette fonction est activée, tous les paramètres **Enregistrements à inclure** sont désactivés dans la boîte de dialogue du rapport **Top 100**. |
| Gestion des entrepôts | Prise en charge de l’unité d’échelle pour la mise en production dans l’entrepôt des commandes sortantes | Lorsque cette fonction est activée, les commandes sortantes peuvent être mises en production directement du hub vers l’unité d’échelle à partir de laquelle les commandes vont être traitées. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les rubriques d’aide suivantes. Ces rubriques ne sont pas nécessairement liées aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans la section précédente. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Rubriques nouvelles ou mises à jour |
|---|---|
| Gestion des modifications d’ingénierie | Les attributs d’ingénierie et la recherche d’attributs d’ingénierie [Attributs d’ingénierie et recherche d’attributs d’ingénierie](../engineering-change-management/engineering-attributes-and-search.md) décrivent maintenant comment fonctionne l’héritage des attributs d’ingénierie. |
| Planification générale | [Plan directeur avec prévisions de la demande](../master-planning/planning-optimization/demand-forecast.md) et [Clés de réduction des prévisions](../master-planning/reduction-keys.md) fournissent maintenant plus d’informations sur la façon de travailler avec les clés de réduction. |
| Planification générale | [Remplissage du stock de sécurité pour les articles](../master-planning/safety-stock-replenishment.md) fournit désormais plus d’informations sur l’utilisation des clés minimum/maximum. |
| Planification générale | [Prévisions de stock](../master-planning/inventory-forecast.md) fournit désormais plus d’informations sur l’allocation des prévisions. |
| Planification générale | [Programme d’approvisionnement](../master-planning/supply-schedule.md) |
| Gestion des entrepôts | [Paramètres globaux des appareils mobiles](../warehousing/mobile-device-parameters.md) |
| Gestion des entrepôts | [Ancrage](../warehousing/anchoring.md) |
| Ventes et marketing | Le commerce interentreprises est maintenant décrit en détail, en commençant par [Mettre en place des échanges interentreprises](../sales-marketing/intercompany-trade-set-up.md) et ce sont des sujets connexes. |
| Gestion des stocks | La documentation sur la visibilité du stock a été étendue et mise à jour, en commençant par [Présentation du complément de visibilité de stock](../inventory/inventory-visibility.md) et ce sont des sujets connexes. |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.23 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.23 des applications Finance and Operations (novembre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.23, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

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
