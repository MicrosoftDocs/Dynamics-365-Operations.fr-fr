---
title: Nouveautés ou modifications apportées dans Dynamics 365 Supply Chain Management, version 10.0.19 (juin 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 86735065864149df27cd3d8b03451ace773af048
ms.sourcegitcommit: b5f2d88ff4e0a234fa6b9ee33516425e54ff2c3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2021
ms.locfileid: "7506853"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Nouveautés ou modifications apportées dans Dynamics 365 Supply Chain Management, version 10.0.19 (juin 2021)

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.19. Cette version a un numéro de build de 10.0.837 et est disponible comme suit :

- **Version préliminaire :** avril 2021
- **Disponibilité générale de la version (mise à jour automatique) :** juin 2021
- **Disponibilité générale de la version (mise à jour automatique) :** juin 2021

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités comprises dans cette version. La colonne *Fonctionnalité* fournit des liens vers le [programme de publication](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), où vous pouvez voir les dates de lancement officiel de chaque fonctionnalité. La colonne *Plus d’informations* fournit plus de détails et/ou de liens vers la documentation connexe.

La plupart de ces fonctionnalités doivent être activées à l’aide de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) avant de pouvoir les utiliser.

| Fonctionnalités | Fonctionnalité | Informations supplémentaires |
|---|---|---|
| Inventaire&nbsp;et&nbsp;logistique | [Approuver et enregistrer les coordonnées bancaires soumises par le fournisseur](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [Tenir à jour les informations de compte bancaire du fournisseur](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| Inventaire et logistique | [Optimisation de l’exportation de l’entité de données des contacts](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | Lorsque cette fonctionnalité est activée, les modifications des données référencées n’entraîneront pas l’ajout des contacts associés dans la prochaine exportation incrémentielle. Lorsque cette fonctionnalité est désactivée, les modifications des données référencées entraîneront l’ajout des contacts associés dans la prochaine exportation incrémentielle. |
| Inventaire et logistique | [Améliorations incrémentielles des capacités d’exécution de l’entrepôt avec des unités d’échelle](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Messages du processeur de messages](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Ajustement du stock de l’entrepôt](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Inventaire et logistique | [Fonctionnalité de recherche pour les champs Introduction au document et Conclusion du document sur la page Devis de vente](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Cette fonction ajoute une fonctionnalité de recherche pour les champs **Introduction au document** et **Conclusion du document** de la page **Devis de vente**.<br><br>Cette fonctionnalité est activée par défaut. |
| Inventaire et logistique | [Exécution en entrepôt avec des unités d’échelle de périphérie sur votre matériel personnalisé](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Déployer des unités d’échelle de périphérie sur du matériel personnalisé à l’aide de LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Fabrication | [Contrôle et suivi de la production avec des unités d’échelle de périphérie sur votre matériel personnalisé](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Déployer des unités d’échelle de périphérie sur du matériel personnalisé à l’aide de LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planification | Confirmation de commande prévisionnelle basée sur une requête | [Commandes prévisionnelles confirmées](../master-planning/planning-optimization/planned-order-firming.md) |
| Gestion des informations sur les produits | [Améliorations de la page de suggestions de variante](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Créer des variantes de produits prédéfinies](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire). Si vous souhaitez utiliser l’une de ces fonctionnalités, vous devez l’activer explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Fonctionnalités | Nom&nbsp;de la fonctionnalité&nbsp;dans Gestion&nbsp;des fonctionnalités | Informations supplémentaires |
|---|---|---|
| Ventes et marketing | Améliorations des performances de nettoyage de l’historique des ventes | Le nettoyage de l’historique des ventes peut prendre beaucoup de temps s’il est rarement exécuté dans les environnements avec un volume important de mises à jour des ventes. Pour réduire la durée et améliorer la fiabilité, cette fonctionnalité divise le nettoyage en lots qui s’exécutent sur une durée limitée. Dans la mesure du possible, les capacités de la base de données seront exploitées pour réduire le blocage et éviter de joindre des tables transactionnelles pendant le nettoyage. |
| Ventes et marketing | Mettre à jour la date de réception demandée avec la date confirmée pour les commandes intersociétés | Cette fonctionnalité vous permet de contrôler ce qu’il adviendra des valeurs du champ de vente et d’achat lors de l’utilisation de la livraison directe intersociétés. Vous pouvez choisir si le système mettra à jour les dates demandées ou ignorera leur mise à jour. Si vous ignorez la mise à jour, les dates demandées représenteront ce que le client a demandé. Si vous activez la mise à jour, les dates demandées (lors de l’utilisation du contrôle de date de livraison) ne représentent que ce que le client a demandé initialement. Le contrôle de date de livraison, s’il est différent de *Aucun*, annulera ce qui a été initialement demandé. Vous pouvez définir cette option à l’aide du nouveau paramètre **Mettre à jour la date de réception demandée avec la date confirmée** dans les paramètres du fournisseur ou du client intersociétés.<br><br>Si la fonctionnalité est désactivée, le système remplacera la date de réception demandée dans les commandes client d’origine en fonction de la règle du contrôle de date de livraison, mais la date d’expédition demandée restera telle quelle. |
| Gestion des entrepôts | Arrondir les quantités vers le bas pour l’unité de vente la plus proche à la libération dans l’entrepôt | Cette fonctionnalité ajoute une option qui peut restreindre les quantités des commandes lors du lancement dans l’entrepôt. Lorsque cette fonctionnalité est activée, les quantités des commandes seront arrondies à l’unité de vente entière la plus proche et les commandes incluant des quantités pour moins d’une unité de vente seront rejetées pour lancement. |
| Gestion des entrepôts | Méthode de vague « Création de travail planifié » pour l’ensemble de l’organisation | Lors de l’activation de cette fonctionnalité, la méthode de vague *Planifier la création du travail* sera configurée pour s’exécuter en parallèle dans toutes les entités juridiques. Plusieurs paramètres supplémentaires seront également affectés. Pour obtenir des détails complets, consultez [Planifier la création du travail pendant la vague](../warehousing/configure-wave-schedule-work-creation.md). |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les rubriques d’aide suivantes. Ils ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans la section précédente, mais ils peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Rubriques nouvelles ou mises à jour |
|---|---|
| Gestion des modifications d’ingénierie | [FAQ sur la gestion des modifications d’ingénierie](../engineering-change-management/change-management-faq.md) |
| Approvisionnements | [Demandes de catégorie des fournisseurs](../procurement/category-requests-from-vendors.md) |
| Gestion des informations sur les produits | [Gérer l’unité de mesure](../pim/tasks/manage-unit-measure.md)<br><br>[Calculs du modèle de configuration de produit](../pim/config-model-calculations.md) |
| Contrôle de la production | [Souche de numéros unifiés pour les ID tâche](../production-control/unified-job-ids.md) |
| Gestion du transport | [Classes de charge partielle](../transportation/ltl-class.md)<br><br>[Codes NMFC](../transportation/nmfc-codes.md) |
| Gestion des entrepôts, création et traitement de vagues | [Création et traitement des vagues](../warehousing/wave-processing.md)<br><br>[Paramètres d’entrepôt pour le traitement des vagues](../warehousing/wave-warehouse-parameters.md)<br><br>[Modèles de vague](../warehousing/wave-templates.md)<br><br>[Répartition des vagues](../warehousing/wave-allocation-method.md)<br><br>[Planifier la création du travail pendant la vague](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Mise en conteneur](../warehousing/wave-containerization.md)<br><br>[Notifications d’exécution de vague](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.19 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.19 des applications Finance and Operations (juin 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.19, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

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
