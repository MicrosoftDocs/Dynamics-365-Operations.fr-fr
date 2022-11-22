---
title: Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.29 (octobre 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.29.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 8f6ba18096cffe907c339ad525c99535bc5ee568
ms.sourcegitcommit: 7745c4bd3ab3aace4b4cb814eaf0cfdbae4a0cbd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9784689"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10029-october-2022"></a>Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.29 (octobre 2022)

[!include [banner](../includes/banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.29. Cette version a un numéro de build de 10.0.1326 et est disponible selon le programme suivant :

- **Version préliminaire :** Août 2022
- **Disponibilité générale de la version (mise à jour manuelle) :** Septembre 2022
- **Disponibilité générale de la version (mise à jour automatique) :** Octobre 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Inventaire et logistique | [Allouer et réserver des articles WMS dans la visibilité des stocks](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | [Prise en charge de la Inventory Visibility pour les articles WMS](../inventory/inventory-visibility-whs-support.md) | Activé par défaut |
| Inventaire et logistique | [Précharger des listes d’inventaire disponibles simplifiées](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | [Utiliser l’application Inventory Visibility](../inventory/inventory-visibility-power-platform.md) | Activé par la configuration du service |
| Automatisation de l’approvisionnement sur commande | [Automatisation de l’approvisionnement sur commande](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Automatisation de l’approvisionnement sur commande](../master-planning/make-to-order-supply-automation.md) | Gestion des fonctions :<br>*Automatisation de l’approvisionnement sur commande* |
| Planification | [Afficher et appliquer des aperçus détaillés pour DDMRP](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Vue d’ensemble de la planification des besoins en matériaux basée sur la demande (DDMRP)](../master-planning/planning-optimization/ddmrp-overview.md) | Gestion des fonctions :<br>*(Version préliminaire) DDMRP pour Optimisation de la planification* |
| Contrôle de la production | [Rendre les marchandises finies physiquement disponibles avant la validation dans les journaux](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Rendre les marchandises finies physiquement disponibles avant la validation dans les journaux](../production-control/deferred-posting.md) | Gestion des fonctions :<br>*(Version préliminaire) Rendre les produits finis physiquement disponibles avant la validation dans les journaux* |
| Gestion des entrepôts | [Rechercher des données pertinentes dans le warehouse mobile app](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Requêter des données en utilisant des détours de Warehouse Management mobile app](../warehousing/warehouse-app-data-inquiry.md) | Gestion des fonctions :<br>*Flux de recherche de données de l’application Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Gestion des coûts | Optimisation du calcul des prix en attente du co-produit | Cette fonctionnalité résout un conflit qui peut parfois se produire lorsque les prix des co-produits sont calculés à l’aide de fils multiples. Cela amène le système à s’assurer que le prix de chaque co-produit n’est calculé qu’une seule fois. Le résultat de ce calcul est ensuite utilisé comme entrée pour tous les autres calculs. Si un prix en attente existe déjà, ce prix est utilisé. |
| Planification générale | Regrouper les transactions dans l’optimisation de la planification | Cette fonctionnalité peut aider à réduire le nombre d’ordres planifiés générés pour fournir une seule ligne de commande client lorsque vous utilisez l’optimisation de la planification. Lorsque cette fonctionnalité est activée, l’optimisation de la planification regroupe toutes les transactions de stock pour une ligne de commande en un seul besoin pour la quantité totale. (Ce comportement correspond au comportement du moteur de planification intégré.) L’offre et la demande sont regroupées séparément. Par conséquent, la fonctionnalité permet de réduire le volume de transactions lorsque vous avez des transactions fractionnées et lorsque vous utilisez des dimensions (telles que des numéros de lot ou des numéros de série) qui ne sont pas des dimensions de couverture. |
| Approvisionnements | Mettre le fournisseur en attente pour les commandes fournisseur | Cette fonctionnalité vous permet de mettre un fournisseur en attente pour les bons de commande. Elle ajoute un nouveau type de blocage *Commande fournisseur* qui marque un fournisseur comme étant en attente pour les commandes fournisseur. Vous ne pourrez pas créer de nouvelles commandes fournisseur pour les fournisseurs qui sont en attente de commandes fournisseur, mais vous pourrez toujours traiter les factures ou les paiements en cours pour ces fournisseurs. |
| Ventes et marketing | Calculer le montant net de la ligne lors de l’importation | Cette fonction vous permet de contrôler si le système doit recalculer les totaux des lignes lorsque vous importez des données via l’entité *Lignes de commande client*, *Lignes de devis de vente*, ou *Lignes de commande de retour* en utilisant OData ou double écriture. Cela n’a d’effet que lorsque vous avez également des politiques d’évaluation des accords commerciaux en place qui limitent les changements au champ **Montant net** pour les lignes de commande client, de devis de vente, et/ou de commande de retour. Il ajoute un paramètre appelé **Calculer le montant net de la ligne** à la page **Comptabilité client> de configuration > paramètres de comptabilité client**. Lorsque ce paramètre est réglé sur *Oui*, le système recalculera toujours les montants de la ligne si nécessaire (ignorant ainsi toute politique d’évaluation d’accord commercial pour le montant net de la ligne). Lorsque le paramètre est réglé sur *Non*, le système ne calculera jamais automatiquement le montant net de la ligne, même si des modifications entrantes du prix de la ligne, de la quantité et/ou de la remise impliquent que le montant net de la ligne doit être recalculé. Cette fonctionnalité est activée par défaut et définit initialement **Calculer le montant net de la ligne** à *Oui*. Le paramètre *Non* correspond au comportement du système avant la version 10.0.23 et est fourni principalement pour prendre en charge les scénarios hérités d’intégration.<br><br>Pour plus d’informations, voir [Recalculer les montants nets des lignes lors de l’importation des commandes client, des devis, et des retours](../sales-marketing/calc-line-net-amounts-import.md). |
| Ventes et marketing | Calculer les totaux de vente à l’aide de threads multiples | Cette fonction permet d’améliorer les performances en permettant au système d’utiliser le traitement parallèle lorsqu’il calcule les totaux des ventes dans un lot. La fonctionnalité ajoute un nouveau champ **Nombre de fils** à la boite de dialogue **Calculer le total des ventes**. Si vous choisissez d’exécuter le calcul dans un lot, vous pouvez utiliser ce champ pour définir le nombre maximal de threads. Si vous définissez la valeur sur *0* (zéro) ou *1*, un seul fil sera utilisé. Les valeurs supérieures à 1 activent le traitement multifilière. |
| Ventes et marketing | Mettre à jour les prix et les remises entrés manuellement pour les commandes intersociétés | Cette fonctionnalité ajoute le support pour les politiques de modification manuelle pour les commandes intersociétés. Elle inclut le support pour le transfert des politiques de modification manuelle entre les ventes intersociétés et les commandes fournisseurs. Auparavant, les politiques de modification manuelle n’étaient prises en charge que pour les commandes non intersociétés. Lorsque cette fonctionnalité est activée, le système vous offrira la possibilité de mettre à jour les prix et les remises après que vous ayez enregistré les modifications apportées à une commande intersociétés. Cette option vous permet de choisir si vous souhaitez appliquer les nouveaux prix et détails des remises à la commande intersociétés ou laisser la commande inchangée. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les articles d’aide suivants. Ces articles ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans les sections précédentes. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Articles nouveaux ou mis à jour |
|---|---|
| Planification générale, CTP | [Calculer les dates de livraison des commandes clients à l’aide de CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Planification générale, DDMRP | [Vue d’ensemble de la planification des besoins en matériaux basée sur la demande (DDMRP)](../master-planning/planning-optimization/ddmrp-overview.md)<br>[Activer la fonction DDMRP pour votre système](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Positionnement du stock](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Profil et niveaux de tampon](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Planification pilotée par la demande](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Exécution visuelle et collaborative](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Gestion des entrepôts | [Emballage de conteneurs pour expédition](../warehousing/packing-containers.md)<br>[Travaux d’emballage pour l’emballage des conteneurs sortants et le traitement des expéditions](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Modifications de l’état de la fonctionnalité dans cette version

Le tableau suivant répertorie les fonctionnalités qui sont devenues obligatoires ou activées par défaut dans la version 10.0.29. Toutes ces fonctionnalités seront automatiquement activées pour votre système dès que vous effectuez la mise à jour vers la version 10.0.29. Les fonctionnalités obligatoires ne peuvent pas être désactivées, mais les fonctionnalités activées par défaut peuvent toujours être désactivées en utilisant [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Le tableau répertorie également les fonctionnalités qui étaient auparavant en version préliminaire publique, mais qui ont été modifiées pour devenir généralement disponibles dans la version 10.0.29. Cette modification indique que les fonctionnalités sont désormais recommandées pour utilisation dans des environnements de production. Ces fonctionnalités sont désactivées par défaut, sauf indication contraire. Vous devez donc utiliser [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour les activer si vous souhaiter les utiliser.

| Module | Nom de la fonction | Statut de la nouvelle fonctionnalité |
| --- | --- | --- |
| Gestion des actifs | [Fonctionnalité de gestion d’actifs pour l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Gestion des coûts | [Remplacer le libellé de l’annulation dans Clôture et ajustement par Contrepasser](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Obligatoire |
| Gestion des coûts | Nettoyer les détails du calcul de la nomenclature des versions de coûts croisés | Obligatoire |
| Gestion des coûts | [Comparer le stockage du prix des articles](../cost-management/compare-item-price.md) | Obligatoire |
| Gestion des coûts | [Niveau de calcul des coûts](../cost-management/cost-calculation-level.md) | Activé par défaut |
| Gestion des coûts | Activer le paramétrage des numéros de traitement par lots défini par l’utilisateur pour la contrepassation de la clôture du stock | Activé par défaut |
| Gestion des coûts | [Détails de la progression de la clôture du stock](whats-new-scm-10-0-21.md) | Activé par défaut |
| Gestion des coûts | [Stockage de l’état de valeur de stock](../cost-management/inventory-value-report-storage.md) | Obligatoire |
| Gestion des coûts | Nettoyage des données de l’état de valeur de stock | Obligatoire |
| Gestion des coûts | Moyenne mobile, séquence de coût de secours | Obligatoire |
| Gestion des coûts | Afficher le journal de clôture dans la grille | Obligatoire |
| Gestion des coûts | Afficher les articles avec des transactions qui n’ont pas été entièrement réglées dans un format de synthèse | Obligatoire |
| Gestion des entrepôts et des stocks | Autoriser les valeurs d’attributs de lot vides | Obligatoire |
| Gestion des entrepôts et des stocks | Incrémenter automatiquement les numéros de ligne des lignes d’ordre de transfert de stock | Obligatoire |
| Gestion des entrepôts et des stocks | Créer un ordre de transfert à partir de la ligne de vente | Obligatoire |
| Gestion des entrepôts et des stocks | Désactiver le champ de ligne de journal de stock dans le flux de travail | Obligatoire |
| Gestion des entrepôts et des stocks | Activer la fonction d’avertissement des paramètres de gestion de la qualité du stock | Obligatoire |
| Gestion des entrepôts et des stocks | (Chine) Exclure la réception physique et les coûts d’émission du coût moyen mensuel | Activé par défaut |
| Gestion des entrepôts et des stocks | [Workflow d’approbation du journal de stock](../inventory/inventory-journal-workflow.md) | Obligatoire |
| Gestion des entrepôts et des stocks | [Stockage des états sur le stock disponible](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Obligatoire |
| Gestion des entrepôts et des stocks | [Vues enregistrées pour la gestion de stock](saved-views-scm.md) | Obligatoire |
| Gestion des entrepôts et des stocks | Transférer l’annulation de commande | Obligatoire |
| Gestion des entrepôts et des stocks | Utilisation de l’unité de mesure et de la quantité d’unités dans les journaux de stock | Obligatoire |
| Gestion des entrepôts et des stocks | Déverrouiller le journal de stock | Obligatoire |
| Fabrication | [Prélèvement automatique des matières activées pour les entrepôts pour les prélèvements automatiquement validés](whats-new-scm-10-0-23.md) | Disponibilité générale |
| Fabrication | Activer l’affichage des dimensions de stock dans la liste des matières pour les opérations de gamme de production | Obligatoire |
| Fabrication | [Ce bouton permet d’entrer des numéros de lot et de série lors de la déclaration de fin à partir du périphérique de bons de travail](../production-control/report-finished-job-device.md) | Activé par défaut |
| Fabrication | Prélèvement de la quantité en poids variable de production amélioré | Activé par défaut |
| Fabrication | [Recherche de tâche pour l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Fabrication | [Intégration de système d’exécution de fabrication](../production-control/mes-integration.md) | Activé par défaut |
| Fabrication | [Vue « Ma journée » pour l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Activé par défaut |
| Fabrication | [Vérification de la disponibilité des matériaux à la demande pour les ordres de fabrication](whats-new-scm-10-0-24.md) | Activé par défaut |
| Fabrication | [Remplacer la réservation de production par défaut](../production-control/override-default-reservation-principle.md) | Obligatoire |
| Fabrication | [Enregistrer la consommation des matériaux sur l’interface d’exécution de l’atelier de production (autre que WMS)](../production-control/production-floor-execution-configure.md) | Disponibilité générale |
| Fabrication | [État sur les articles en poids variable à partir de l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Disponibilité générale |
| Fabrication | [État sur les co-produits et sous-produits de l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Activé par défaut |
| Fabrication | [Générer un état sur les éléments de planification dans l’interface d’exécution à l’atelier de production](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | Activé par défaut |
| Fabrication | [Vues enregistrées pour le contrôle de la production](saved-views-scm.md) | Obligatoire |
| Fabrication | [Afficher les numéros de série, de traitements par lots et de contenants complets dans l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Fabrication | [Valider l’expiration des matières premières par rapport à la date de consommation prévue](whats-new-scm-10-0-23.md) | Activé par défaut |
| Planification générale | [Confirmation automatique pour l’optimisation de la planification](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoire |
| Planification générale | [Confirmation et consolidation pouvant être traitées par lots pour les lots de commandes planifiées de consommables et d’articles emballés](whats-new-scm-10-0-20.md) | Activé par défaut |
| Planification générale | [Inclure les articles avec stock disponible lorsque les filtres de pré-traitement sont activés](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | Activé par défaut |
| Planification générale | [Planification des capacités infinies pour l’optimisation de la planification](../master-planning/planning-optimization/infinite-capacity-planning.md) | Activé par défaut |
| Planification générale | [Marges pour Optimisation de la planification](../master-planning/planning-optimization/safety-margins.md) | Obligatoire |
| Planification générale | [Jours négatifs pour l’optimisation de la planification](../master-planning/planning-optimization/delay-tolerance.md) | Obligatoire |
| Planification générale | [Autorisation parallèle de l’ajustement de la prévision de la demande](whats-new-scm-10-0-20.md) | Obligatoire |
| Planification générale | [Confirmation de l’ordre planifié avec filtrage](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoire |
| Planification générale | [Ordres de fabrication prévisionnels pour l’optimisation de la planification](../master-planning/planning-optimization/production-planning.md) | Obligatoire |
| Planification générale | [Accords commerciaux d’achat pour l’optimisation de la planification](../master-planning/planning-optimization/purchase-trade-agreement.md) | Obligatoire |
| Planification générale | [Vues enregistrées des ordres prévisionnels](saved-views-scm.md) | Obligatoire |
| Approvisionnements | Frais de et vers les montants sur les commandes fournisseur | Obligatoire |
| Approvisionnements | Désactiver le bouton de réinitialisation de la répartition de demande d’achat | Activé par défaut |
| Approvisionnements | [Activer la réinitialisation des flux de travail liés à l’approvisionnement](whats-new-scm-10-0-20.md) | Activé par défaut |
| Approvisionnements | [Limiter le nombre de lignes des commandes fournisseur par tâche de traitement par lots](whats-new-scm-10-0-27.md) | Activé par défaut |
| Approvisionnements | [Fusionner les dimensions financières du fournisseur avec la dimension financière de lien de dimension active sur la commande fournisseur](whats-new-scm-10-0-25.md) | Obligatoire |
| Approvisionnements | [Valider les quantités enregistrées de produits stockés et les restes de produits non stockés pour les réceptions et les factures fournisseur](whats-new-scm-10-0-26.md) | Disponibilité générale |
| Approvisionnements | [Empêcher la surconsommation des réservations budgétaires générales lorsque le flux de travail contient plusieurs demandes d’achat](whats-new-scm-10-0-21.md) | Activé par défaut |
| Approvisionnements | [Partie responsable du contrat d’achat](../procurement/purchase-agreements.md) | Obligatoire |
| Approvisionnements | [Vues enregistrées pour les commandes fournisseur](saved-views-scm.md) | Obligatoire |
| Gestion des informations sur les produits | Pré-traitement de l’état de nomenclature afin d’éviter les délais d’attente | Obligatoire |
| Gestion des informations sur les produits | Définir les dimensions financières par défaut séparément lors de l’utilisation des modèles d’article | Obligatoire |
| Gestion des informations sur les produits | Activer les groupes de dimensions de produit pour les modèles d’article | Obligatoire |
| Gestion des informations sur les produits | Article - Améliorations de l’entité code-barres | Obligatoire |
| Gestion des informations sur les produits | Régénérer les noms de variantes de produit en fonction de la nomenclature | Obligatoire |
| Gestion des informations sur les produits | [Vues enregistrées pour les produits lancés](saved-views-scm.md) | Obligatoire |
| Gestion des informations sur les produits | [Améliorations de la page de suggestions de variante](../pim/tasks/create-predefined-product-variants.md) | Obligatoire |
| Ventes et marketing | [Répartition des frais sur une commande client](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Obligatoire |
| Ventes et marketing | Nettoyer l’historique des mises à jour des commandes clients | Obligatoire |
| Ventes et marketing | [Nettoyer l’historique des mises à jour de ventes selon l’âge](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Obligatoire |
| Ventes et marketing | [Optimisation de l’exportation de l’entité de données des contacts](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Obligatoire |
| Ventes et marketing | Copier le groupe de remises totales pour l’avoir sur vente | Obligatoire |
| Ventes et marketing | [Activer la recherche pour les champs d’introduction et de conclusion du document du devis de vente](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Obligatoire |
| Ventes et marketing | [Améliorer les performances de l’état des « 100 principaux clients »](whats-new-scm-10-0-23.md) | Obligatoire |
| Ventes et marketing | Inclure les enregistrements en attente dans les tâches de nettoyage de l’historique | Obligatoire |
| Ventes et marketing | Limiter le nombre de lignes des commandes client par tâche de traitement par lots | Activé par défaut |
| Ventes et marketing | [Limiter le nombre de commandes clients qui peuvent être sélectionnées pour validation](whats-new-scm-10-0-21.md) | Obligatoire |
| Ventes et marketing | Recalculer le solde client estimé | Obligatoire |
| Ventes et marketing | [Enregistrement de la ligne de commande client de retour avec précision décimale avec et sans poids variable](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Obligatoire |
| Ventes et marketing | [Vues enregistrées pour la vente et le marketing](saved-views-scm.md) | Obligatoire |
| Ventes et marketing | [Confirmation de commande client en un seul clic](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Obligatoire |
| Gestion du transport | Autoriser le non-rapprochement des factures de transport à partir des lignes de facture de transport sans journal des factures fournisseur validé | Activé par défaut |
| Gestion du transport | [Activer la création d’un journal des factures fournisseur lorsqu’une facture des frais de transport est ignorée](whats-new-scm-10-0-20.md) | Activé par défaut |
| Gestion du transport | [Expédition de petits colis](../warehousing/small-parcel-shipping.md) | Obligatoire |
| Gestion du transport | [Certification USMCA du document d’origine](../transportation/usmca-certification-of-origin.md) | Activé par défaut |
| Gestion des entrepôts | [Zone d’emplacement supplémentaire](../warehousing/additional-location-zones.md) | Obligatoire |
| Gestion des entrepôts | [Annuler le travail](../warehousing/cancel-warehouse-work.md) | Obligatoire |
| Gestion des entrepôts | [Consolider l’expédition](../warehousing/configure-shipment-consolidation-policies.md) | Obligatoire |
| Gestion des entrepôts | [Créer et traiter les ordres de transfert à partir de l’application d’entrepôt](../warehousing/create-transfer-order-from-warehouse-app.md) | Obligatoire |
| Gestion des entrepôts | Modèles de cross-docking avec instructions d’emplacement | Activé par défaut |
| Gestion des entrepôts | [Découpler le travail de rangement des APE](whats-new-scm-10-0-21.md) | Obligatoire |
| Gestion des entrepôts | [Opérations put différées](../warehousing/deferred-processing-manual-inventory-movement.md) | Obligatoire |
| Gestion des entrepôts | Placement différé - conteneur | Activé par défaut |
| Gestion des entrepôts | Traitement du placement différé : activez-le pour la fonction de modèle d’audit lorsque l’événement de déclenchement est défini sur Antérieur | Obligatoire |
| Gestion des entrepôts | [Désactiver les réceptions prévues à partir d’ordres de qualité qui échantillonnent le stock bloqué](../inventory/inventory-blocking.md) | Activé par défaut |
| Gestion des entrepôts | Activer le contrôle rapide pour les appareils mobiles d’entrepôt | Obligatoire |
| Gestion des entrepôts | [Analyseur amélioré pour les codes-barres GS1](../warehousing/gs1-barcodes.md) | Disponibilité générale |
| Gestion des entrepôts | [Réservation flexible de contenants validée par commande](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obligatoire |
| Gestion des entrepôts | [Réservation de dimension de niveau entrepôt flexible](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obligatoire |
| Gestion des entrepôts | [Utilisation de l’emplacement de consolidation des articles](../warehousing/item-consolidation-location-utilization.md) | Activé par défaut |
| Gestion des entrepôts | Historique de réception de contenant | Activé par défaut |
| Gestion des entrepôts | [Consolidation d’expédition manuelle](../warehousing/consolidate-shipments-manual-workbench.md) | Activé par défaut |
| Gestion des entrepôts | [Service de prélèvement de ligne de transfert manuel pour les administrateurs ou les utilisateurs approuvés similaires](whats-new-scm-10-0-28.md) | Disponibilité générale |
| Gestion des entrepôts | [Interface de l’équipement de manutention du matériel](../warehousing/mhax.md) | Obligatoire |
| Gestion des entrepôts | [Nouvelles pages de l’atelier de planification des chargements](whats-new-scm-10-0-24.md) | Disponibilité générale |
| Gestion des entrepôts | [Visualisation de la charge de travail sortante](../warehousing/outbound-workload-visualization.md) | Obligatoire |
| Gestion des entrepôts | [Cross-docking planifié](../warehousing/planned-cross-docking.md) | Obligatoire |
| Gestion des entrepôts | [Traiter les événements d’application d’entrepôt](../warehousing/warehouse-app-events.md) | Obligatoire |
| Gestion des entrepôts | Amélioration des requêtes pour le modèle de travail de rangement des coproduits et des sous-produits | Obligatoire |
| Gestion des entrepôts | [Arrondir les quantités vers le bas pour l’unité de vente la plus proche à la libération dans l’entrepôt](whats-new-scm-10-0-19.md) | Obligatoire |
| Gestion des entrepôts | [Vue enregistrée pour l’atelier de planification des chargements](saved-views-scm.md) | Obligatoire |
| Gestion des entrepôts | [Vue enregistrée pour la page des détails du travail](saved-views-scm.md) | Obligatoire |
| Gestion des entrepôts | [Vue enregistrée pour le traitement de la vague](saved-views-scm.md) | Obligatoire |
| Gestion des entrepôts | [Vues enregistrées pour le traitement du chargement](saved-views-scm.md) | Obligatoire |
| Gestion des entrepôts | [Vues enregistrées pour le traitement de l’expédition](saved-views-scm.md) | Obligatoire |
| Gestion des entrepôts | [Scanner les codes-barres de GS1](../warehousing/gs1-barcodes.md) | Disponibilité générale |
| Gestion des entrepôts | Détails de l’étiquette de la vague d’expédition | Obligatoire |
| Gestion des entrepôts | [Insérer des créneaux dans les unités mixtes](whats-new-scm-10-0-21.md) | Obligatoire |
| Gestion des entrepôts | [Utiliser une API plus rapide pour la clôture/réouverture des conteneurs sur la station de conditionnement](whats-new-scm-10-0-21.md) | Activé par défaut |
| Gestion des entrepôts | [Valider les modèles sélectionnés pour les tâches de réapprovisionnement](whats-new-scm-10-0-20.md) | Activé par défaut |
| Gestion des entrepôts | [Champs promus de l’application Warehouse](../warehousing/warehouse-app-promoted-fields.md) | Obligatoire |
| Gestion des entrepôts | [Instructions d’étape de l’application d’entrepôt](../warehousing/mobile-app-titles-instructions.md) | Obligatoire |
| Gestion des entrepôts | [Statut de l’emplacement de l’entrepôt](../warehousing/warehouse-location-status.md) | Obligatoire |
| Gestion des entrepôts | [Détours de l’application Warehouse Management](../warehousing/warehouse-app-detours.md) | Activé par défaut |
| Gestion des entrepôts | [Détails du traitement par lots des vagues](../warehousing/wave-processing.md) | Obligatoire |
| Gestion des entrepôts | [Notifications d’exécution de vague](../warehousing/wave-execution-notifications.md) | Obligatoire |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.29 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.29 (octobre 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de la version 10.0.29, connectez-vous à Lifecycle Services (LCS) et consultez l’ [Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 et les clouds du secteur : plan de la 1e vague de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2022](/dynamics365-release-plan/2022wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

L’article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l’article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
