---
title: Version préliminaire de Dynamics 365 Supply Chain Management 10.0.21 (octobre 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 42d296cb0402b5e96f23d628f08a28fb35683d5f
ms.sourcegitcommit: 5a44eb4f555bf5ee0b1293f0ecdc37ee8b53aa24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2021
ms.locfileid: "7391206"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10021-october-2021"></a>Version préliminaire de Dynamics 365 Supply Chain Management 10.0.21 (octobre 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire de Microsoft Dynamics 365 Supply Chain Management 10.0.21. Cette version a un numéro de build de 10.0.960 et est disponible comme suit :

- **Version préliminaire :** Août 2021
- **Disponibilité générale de la version (mise à jour manuelle) :** Septembre 2021
- **Disponibilité générale de la version (mise à jour automatique) :** Octobre 2021

## <a name="known-deployment-issue"></a>Problème de déploiement connu

Au moment du déploiement de la version 10.0.21 sur IaaS, vous pouvez recevoir l’avertissement de déploiement suivant :

**Code d’avertissement :** 95017

**Message d’avertissement :** Échec du script \[SetupDiagnostics\] à exécuter la machine virtuelle

Le déploiement fonctionnera malgré l'avertissement. Cependant, les problèmes connus suivants peuvent survenir dans Lifecycle Services (LCS) :

- Sur la page **Surveillance de l’environnement**, le lien **Afficher les informations détaillées sur la version** n’apparaîtra pas, vous ne pourrez donc pas voir les versions spécifiques des modules installés dans votre environnement. Sans ces données, les correctifs ultérieurs peuvent échouer, car le processus qui applique les correctifs utilise ces données pour vérifier que les conditions préalables de la version du module sont remplies. Comme il n’est pas possible d’utiliser la build PEAP/version préliminaire en production ou d’appliquer des correctifs, l’impact devrait être minime.
- Les onglets **Indicateurs de performance** et **Analyse des indices** sur la page **Surveillance de l’environnement** sous SQL Insights n’affichera aucune donnée. Toutes les autres fonctionnalités **Surveillance de l’environnement** fonctionneront comme prévu.
- La page **Diagnostic système complet** ne sera pas accessible. Les données associées sur le statut des exécutions nocturnes du collecteur et les problèmes détectés par ses règles ne s’afficheront pas non plus.

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités comprises dans cette version. La colonne *Fonctionnalité* fournit des liens vers le [programme de publication](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), où vous pouvez voir les dates de lancement officiel de chaque fonctionnalité. La colonne *Plus d’informations* fournit plus de détails et/ou de liens vers la documentation connexe.

La plupart de ces fonctionnalités doivent être activées à l’aide de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) avant de pouvoir les utiliser. Certaines des fonctionnalités répertoriées sont toujours en version préliminaire, tandis que d’autres peuvent déjà être généralement disponibles.

| Fonctionnalités | Fonctionnalité | Informations supplémentaires |
|---|---|---|
| Inventaire&nbsp;et&nbsp;logistique | [Complément Comptabilité globale des stocks pour Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Page d’accueil de la comptabilité globale des stocks](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Valider les ajustements en stock à l’aide de codes de motif configurables connectés aux comptes de contrepartie](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Codes motif d’inventaire de stock](../warehousing/reason-codes-for-counting-journals.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Stratégie d’exportation de données référencées de devis de vente](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Choisissez si les modifications des données référencées par devis entraîneront l’ajout de ces devis (ou lignes) à la prochaine exportation incrémentielle. Vos exportations incrémentielles s’exécuteront plus rapidement si vous choisissez de ne pas inclure de tels devis ou lignes.<br><br>Cette fonctionnalité ajoute un paramètre appelé **Ignorer les données référencées des devis lors du suivi des modifications** sur la page **Paramètres de la Comptabilité client**. |
| Inventaire&nbsp;et&nbsp;logistique | [Scannez les codes-barres dans l’entrepôt en utilisant les normes de format GS1](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [Codes à barres GS1 et codes QR](../warehousing/gs1-barcodes.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Réservation provisoire pour le complément de visibilité des stocks](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Réservations dans la visibilité des stocks](../inventory/inventory-visibility-reservations.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Améliorations des déductions et du poids variable pour la gestion des remises](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Gérer les déductions à l’aide du workbench de déduction](../rebate-management/deduction-workbench.md )<br><br>[Traiter, examiner et valider les remises](../rebate-management/process-review-post.md)<br><br>[Accords de gestion des remises](../rebate-management/rebate-management-deals.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Instructions d’étape de l’application d’entrepôt](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Personnaliser les titres d’étapes et les instructions pour l’application mobile Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Pauses de travail et suivi des mises à jour pour le coût au débarquement](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Suivi des mises à jour pour rangement](../landed-cost/update-tracking-putaway.md )<br><br>[Traitement de marchandises en transit](../landed-cost/in-transit-processing.md) |
| Planification générale | [Jours négatifs pour l’optimisation de la planification](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolérance de retard (jours négatifs)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire). Si vous souhaitez utiliser l’une de ces fonctionnalités, vous devez l’activer explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Fonctionnalités | Nom&nbsp;de la fonctionnalité&nbsp;dans Gestion&nbsp;des fonctionnalités | Informations supplémentaires |
|---|---|---|
| Gestion des coûts | Détails de la progression de la clôture du stock | Cette fonctionnalité d’évaluation permet une vue détaillée de la progression de la clôture des stocks. |
| Approvisionnements | Empêcher la surconsommation des réservations budgétaires générales lorsque le flux de travail contient plusieurs demandes d’achat | Cette fonctionnalité d’évaluation améliore la vérification des erreurs lorsque les utilisateurs soumettent et approuvent des demandes d’achat qui dépassent le solde restant d’une ligne de réservation budgétaire générale. Cela permet d’éviter la surconsommation des réservations budgétaires générales lorsque plusieurs demandes d’achat sont dans le workflow. |
| Contrôle de la production | Afficher les numéros de série, de traitements par lots et de contenants complets dans l’interface d’exécution de l’atelier de production | Cette fonctionnalité offre une expérience améliorée pour l’affichage des listes de n° de série, n° lot et numéros de contenant dans l’interface d’exécution de l’atelier de production. L’affichage passe d’une vue de carte avec un nombre limité de caractères à une vue de liste qui offre suffisamment d’espace pour afficher les valeurs complètes. La liste offre également la possibilité de rechercher des numéros spécifiques. |
| Ventes et marketing | Limiter le nombre de commandes clients qui peuvent être sélectionnées pour validation | Cette fonctionnalité vous permet de définir le nombre maximal de commandes client pouvant être sélectionnées lors de la validation des confirmations, des prélèvements, des bons de livraison et des factures à partir de la page de liste des commandes client. Elle est activée automatiquement. Cette fonctionnalité ajoute un paramètre appelé **Nombre max. de commandes client à valider** dans la page **Paramètres de la comptabilité client**. Le nouveau paramètre prend par défaut une valeur de *100*. Cette fonctionnalité permet d'améliorer les performances de la page de liste des commandes client lorsqu'un nombre important de commandes client est sélectionné. Elle n'a aucun impact sur le nombre de commandes client pouvant être traitées par une tâche périodique. |
| Gestion des entrepôts | Découpler le travail de rangement des APE | Cette fonctionnalité est requise pour envoyer et recevoir des avis d’expédition anticipés (ASN) lorsque vous exécutez une charge de travail de gestion d’entrepôt sur une unité d’échelle (dans le cadre d’une topologie hybride distribuée). Il ajoute une nouvelle table de base de données dédiée au stockage des informations sur le travail de rangement. Auparavant, ces informations étaient stockées dans des tables également utilisées pour les ASN. |
| Gestion des entrepôts | Insérer des créneaux dans les unités mixtes | Permet au système d’insérer des articles dans des emplacements comprenant des unités mixtes (telles que des boîtes et des caisses). Pour chaque ligne de modèle de créneau, cette fonctionnalité vous permet de choisir si la ligne doit positionner les articles à des emplacements à unités mixtes ou à unité unique. |
| Gestion des entrepôts | Utiliser une API plus rapide pour la clôture/réouverture des conteneurs sur la station de conditionnement | Lorsque cette fonctionnalité d’évaluation est activée, les transactions de stock liées aux conteneurs sont créées à l’aide d’un processus léger qui améliore les performances de fermeture ou de réouverture des conteneurs lors du traitement manuel de la station d’emballage. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les rubriques d’aide suivantes. Ils ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans la section précédente, mais ils peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Rubriques nouvelles ou mises à jour |
|---|---|
| Planification générale | [Prévisions de stock](../master-planning/inventory-forecast.md) |
| Planification générale | [Paramètres non utilisés par l’optimisation de la planification](../master-planning/planning-optimization/not-used-parameters.md) |
| Planification générale | [Méthodes de réapprovisionnement et modification de la quantité](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Planification générale | [Planification avec une capacité infinie](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Planification générale | [Afficher l’historique du plan et les journaux de planification](../master-planning/planning-optimization/plan-history-logs.md) |
| Gestion des entrepôts | [Stratégies d’emballage de conteneur](../warehousing/container-packing-strategy-overview.md) |
| Gestion des entrepôts | [Exemples de scénarios d’inventaire tournant](../warehousing/cycle-counting-scenarios.md) |
| Gestion des entrepôts | [Importer les APE entrants via l’entité de données V2](../warehousing/import-asn-v2-data-entity.md) |
| Gestion des entrepôts | [Prélèvement excessif pour les commandes client et les ordres de transfert](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Gestion des entrepôts | [Planifier l’impression d’étiquettes de vague pendant la vague](../warehousing/configure-task-based-wave-label-printing.md) |
| Gestion des entrepôts | [Nouveautés ou modifications dans l’application mobile Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.21 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.21 des applications Finance and Operations (octobre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.21, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

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
