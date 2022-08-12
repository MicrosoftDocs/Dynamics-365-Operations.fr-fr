---
title: Nouveautés et modifications dans Dynamics 365 Supply Chain Management 10.0.25 (avril 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.25.
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c54534ae32aa037f36a16600a058bca6d433002c
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167729"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10025-april-2022"></a>Nouveautés et modifications dans Dynamics 365 Supply Chain Management 10.0.25 (avril 2022)

[!include [banner](../includes/banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.25. Cette version a un numéro de build de 10.0.1149 et est disponible comme suit :

- **Version préliminaire de la version :** février 2022
- **Disponibilité générale de la version (mise à jour automatique) :** mars 2022
- **Disponibilité générale de la version (mise à jour automatique) :** avril 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités qui auront été intégrées à la version après la publication initiale de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Inventaire&nbsp;et&nbsp;logistique | [Améliorations des matières dangereuses](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | Bientôt disponible | Gestion des fonctions :<br>*Améliorations des matières dangereuses* |
| Inventaire&nbsp;et&nbsp;logistique | [Travail de conditionnement pour les stations de conditionnement](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | Bientôt disponible | Gestion des fonctions :<br>*Travail de conditionnement pour les stations de conditionnement* |
| Inventaire&nbsp;et&nbsp;logistique | [Scannez les codes-barres dans l’entrepôt en utilisant les normes de format GS1](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [Codes à barres GS1 et codes QR](../warehousing/gs1-barcodes.md) | Gestion des fonctions :<br>*Scanner les codes-barres de GS1* |
| Fabrication | [Consommation et réservation des matières sur l’interface d’exécution de l’atelier de production](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [Comment les travailleurs utilisent l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-use.md) | Gestion des fonctions :<br>*Enregistrer la consommation des matériaux sur l’interface d’exécution de l’atelier de production (autre que WMS)*<br><br>Et/ou :<br><br>Gestion des fonctions :<br>*(Aperçu) Enregistrer la consommation de matières sur l’interface d’exécution de l’atelier de production (compatible WMS)* |
| Planification | [Maintenance du calendrier centralisé de l’optimisation de la planification](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [Calendriers et planification](../master-planning/supply-chain-calendars-master-planning.md) | Activé par défaut |
| Planification | [Suggestions d’optimisation de la planification pour optimiser l’offre existante](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Messages d’action](../master-planning/action-messages.md) | Activé par défaut |
| Planification | Ordres planifiés simplifiés | [Ordres planifiés simplifiés](../master-planning/planning-optimization/planned-orders-simplified.md ) | Gestion des fonctions :<br>*Ordres planifiés simplifiés* |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Gestion des entrepôts et des stocks | (Pologne) Autoriser la liaison de plusieurs factures SAD à une ligne de commande client dans une seule facture SAD | Cette fonctionnalité vous permet de fractionner les lignes de bon de commande et de les lier à un seul document administratif (DAU) lorsque ces lignes de bon de commande ont été validées pour plusieurs factures différentes (par exemple pour différentes expéditions). |
| Approvisionnements | Consolider plusieurs demandes d’achat dans une seule commande fournisseur par date comptable | Cette fonction permet de regrouper plusieurs demandes d’achat en un seul bon de commande si les différentes demandes d’achat ont des dates comptables différentes. Les règles de stratégie d’achat de création de bon de commande et de consolidation de la demande peuvent être configurées pour automatiser la décision de regrouper les lignes de demande d’approvisionnement par date comptable au niveau du bon de commande. La consolidation des bons de commande par date comptable n’est pas prise en charge si le contrôle budgétaire est activé, car la date comptable est utilisée pour les réservations budgétaires et les engagements. Par conséquent, elle doit être conservée pendant la transition de la demande d’achat à la commande fournisseur. |
| Approvisionnements | Afficher les paramètres de champ de réponse aux appels d’offre par défaut hérités | Cette fonctionnalité réintroduit les paramètres de champ de réponse de demande de devis (appel d’offre) par défaut hérités, qui étaient précédemment supprimés de l’interface utilisateur. Ces paramètres ne fournissent aucune fonctionnalité prête à l’emploi, mais peuvent être personnalisés pour les fournir selon les besoins. Activez cette fonctionnalité si votre organisation a déjà ajouté une fonctionnalité pour les paramètres de champ de réponse d’appel d’offre par défaut ou prévoit de le faire. Lorsque cette fonction est activée, vous pouvez accéder aux paramètres en vous rendant sur la page **Paramètres d’approvisionnement**, en ouvrant l’onglet **Demande de devis** et en sélectionnant **Champs de réponse par défaut à l’appel d’offre**. |
| Approvisionnements | Fusionner les dimensions financières du fournisseur avec la dimension financière de lien de dimension active sur la commande fournisseur | Cette fonction permet de fusionner les dimensions financières du fournisseur avec une dimension financière de lien de dimension active après l’approbation de la demande d’achat si vous définissez un lien entre une dimension financière et une dimension de stock de site. La règle de stratégie d’achat pour la création de commandes fournisseur et la règle de stratégie de consolidation de la demande peut être définie pour fusionner les dimensions financières du fournisseur avec une dimension financière de lien de dimension active au niveau de l’en-tête de commande fournisseur. |
| Contrôle de la production | (Russie) Activer le paramétrage d’emplacement par défaut pour la formule/la nomenclature de production et la réservation/consommation GTD automatique dans la production | La fonctionnalité permet des options supplémentaires pour la production à partir de matières premières importées (localisation russe uniquement) :<ul><li>Option permettant de définir l’emplacement par défaut automatique pour les formules de production et les nomenclatures sur les groupes de ressources et les entrepôts.</li><li>Réservation automatique des matières premières par la dimension *Numéro GTD* dans les entrepôts activés par WMS selon l’algorithme de réservation non-WMS. Ceci s’applique dans les cas où une politique de travail pour *Prélèvement de matières premières* existe avec **Méthode de création de travail** défini sur *Jamais* et la configuration de l’entrepôt, de l’emplacement et du numéro d’article correspond aux transactions de stock de l’ordre de production (traitement par lots).</li><li>Consommation automatique de matières premières par dimension *Numéro GTD* lors de la validation du prélèvement, selon la réservation acquise décrite précédemment.</li></ul> |
| Gestion des entrepôts | (Aperçu) Prise en charge de l’unité d’échelle pour les commandes d’entrepôt entrantes et sortantes | Cette fonctionnalité amène le système à créer des ordres magasin sortants pendant le processus de lancement vers l’entrepôt et à créer des ordres magasin entrants lorsque les ordres de transfert sont validés comme expédiés. Le système synchronise ensuite chaque commande d’entrepôt entrante ou sortante avec l’unité d’échelle responsable de l’expédition ou de la réception de la commande. Notez qu’après avoir activé cette fonctionnalité, vos charges de travail d’exécution d’entrepôt doivent être mises à niveau. Pour plus d’informations, voir [Charges de travail de gestion des entrepôts pour les unités d’échelle cloud et de périphérie](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Cette fonction nécessite la fonctionnalité *Découpler le travail de rangement des APE* et permettra la capacité de recevoir des ordres de transfert à l’aide du processus de réception de contenant sur l’application mobile Warehouse Management. |

## <a name="feature-state-changes-in-this-release"></a>Modifications de l’état de la fonctionnalité dans cette version

Le tableau suivant répertorie les fonctionnalités qui sont devenues obligatoires ou par défaut dans la version 10.0.25. Toutes ces fonctionnalités seront automatiquement activées pour votre système dès que vous effectuerez la mise à jour vers la version 10.0.25. Les fonctionnalités obligatoires ne peuvent pas être désactivées, mais les fonctionnalités activées par défaut peuvent toujours être désactivées à l’aide de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Le tableau répertorie également les fonctionnalités qui étaient auparavant en version préliminaire publique, mais qui ont été modifiées pour devenir généralement disponibles dans la version 10.0.25, ce qui signifie qu’elles sont désormais recommandées pour une utilisation dans les environnements de production. Ces fonctionnalités sont désactivées par défaut, sauf indication contraire, vous devez donc utiliser [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour les activer si vous souhaitez les utiliser.

| Module | Nom de la fonction | État de la fonctionnalité |
| --- | --- | --- |
| Gestion des actifs | [Appliquer des règles pour le regroupement des ordres d’exécution lors de l’exécution d’un plan de maintenance](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Disponibilité générale |
| Gestion des actifs | [Améliorations apportées à la maintenance par compteur](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Disponibilité générale |
| Gestion des coûts | [Niveau de calcul des coûts](../cost-management/cost-calculation-level.md) | Disponibilité générale |
| Gestion des coûts | Activer le paramétrage des numéros de traitement par lots défini par l’utilisateur pour la contrepassation de la clôture du stock | Disponibilité générale |
| Gestion des coûts | [Détails de la progression de la clôture du stock](whats-new-scm-10-0-21.md) | Disponibilité générale |
| Gestion des coûts | [Options des dimensions financières par défaut pour la réévaluation du coût standard du stock](../cost-management/manage-standard-cost-updates.md) | Disponibilité générale |
| Gestion des coûts | Nettoyage des données de l’état de valeur de stock | Activé par défaut |
| Gestion des coûts | [Stockage de l’état de valeur de stock](../cost-management/inventory-value-report-storage.md) | Activé par défaut |
| Gestion des coûts | Afficher le journal de clôture dans la grille | Activé par défaut |
| Gestion des modifications d’ingénierie | [Activer la gestion des changements sur les produits existants](../engineering-change-management/change-management-existing-products.md) | Activé par défaut |
| Gestion des modifications d’ingénierie | [Gestion des modifications d’ingénierie](../engineering-change-management/product-engineering-overview.md) | Activé par défaut |
| Gestion des modifications d’ingénierie | [Notifications d’ingénierie pour la production](../engineering-change-management/engineering-change-management.md) | Activé par défaut |
| Gestion des modifications d’ingénierie | [Amélioration de l’héritage des attributs pour la gestion des changements d’ingénierie](../engineering-change-management/engineering-attributes-and-search.md) | Activé par défaut |
| Gestion des modifications d’ingénierie | [Gérer les modifications apportées aux formules et à leurs ingrédients](../engineering-change-management/manage-formula-changes.md) | Activé par défaut |
| Gestion des modifications d’ingénierie | [Vérifications de la disponibilité du produit](../engineering-change-management/product-readiness.md) | Activé par défaut |
| Gestion des modifications d’ingénierie | [Générer des variantes pour les produits d’ingénierie](../engineering-change-management/engineering-variants.md) | Activé par défaut |
| Gestion des entrepôts et des stocks | Navigation jusqu’à la version de nomenclature à partir des lignes de nomenclature | Obligatoire |
| Planification générale | [Confirmation et consolidation pouvant être traitées par lots pour les lots de commandes planifiées de consommables et d’articles emballés](whats-new-scm-10-0-20.md) | Disponibilité générale |
| Planification générale | Planification des ressources avec la maintenance | Disponibilité générale |
| Planification générale | Activer les fonctionnalités de l’Assistant Paramétrage du plan principal | Obligatoire |
| Planification générale | [Sélection du modèle de prévision sur les détails de prévision de la demande](../master-planning/manual-adjustments-baseline-forecast.md) | Obligatoire |
| Planification générale | [Visualisation de la progression de la planification](../master-planning/tasks/monitor-master-planning-run.md) | Obligatoire |
| Planification générale | [Confirmation de la mise en parallèle des ordres prévisionnels](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoire |
| Planification générale | [Confirmation de l’ordre planifié avec filtrage](../master-planning/planning-optimization/planned-order-firming.md) | Activé par défaut |
| Planification générale | [Vues enregistrées des ordres prévisionnels](saved-views-scm.md) | Activé par défaut |
| Approvisionnements | Désactiver le bouton de réinitialisation de la répartition des demandes d’achat | Disponibilité générale |
| Approvisionnements | [Activer la réinitialisation des flux de travail liés à l’approvisionnement](whats-new-scm-10-0-20.md) | Disponibilité générale |
| Approvisionnements | Possibilité de confirmer les commandes fournisseur acceptées de la collaboration fournisseur par lots | Obligatoire |
| Approvisionnements | Statut Clôturé du contrat d’achat | Obligatoire |
| Approvisionnements | Ajouter des lignes aux factures de CF associées à un contrat d’achat | Activé par défaut |
| Approvisionnements | Ajouter un champ Quantité commandée à la page Validation de l’accusé de réception de marchandises | Activé par défaut |
| Approvisionnements | [Autoriser les fournisseurs à appliquer les catégories d’approvisionnement via la collaboration fournisseur](../procurement/category-requests-from-vendors.md) | Activé par défaut |
| Approvisionnements | Frais des montants De et Vers des commandes fournisseur | Activé par défaut |
| Approvisionnements | Paramétrage des frais avec le site et l’entrepôt | Activé par défaut |
| Approvisionnements | Activer le calcul des droits de douane sur les achats basé sur le tarif annuel | Activé par défaut |
| Approvisionnements | [Partie responsable du contrat d’achat](../procurement/purchase-agreements.md) | Activé par défaut |
| Approvisionnements | [Vues enregistrées pour les commandes fournisseur](saved-views-scm.md) | Activé par défaut |
| Gestion des informations sur les produits | [Contrôle stricte des quantités de commande par défaut](../production-control/default-order-settings.md) | Obligatoire |
| Gestion des informations sur les produits | Pré-traitement de l’état de nomenclature afin d’éviter les délais d’attente | Activé par défaut |
| Gestion des informations sur les produits | Définir les dimensions financières par défaut séparément lors de l’utilisation des modèles d’article | Activé par défaut |
| Gestion des informations sur les produits | Activer les groupes de dimensions de produit pour les modèles d’article | Activé par défaut |
| Gestion des informations sur les produits | Régénérer les noms de variantes de produit en fonction de la nomenclature | Activé par défaut |
| Gestion des informations sur les produits | [Améliorations de la page de suggestions de variante](../pim/tasks/create-predefined-product-variants.md) | Activé par défaut |
| Contrôle de la production | Prélèvement de la quantité en poids variable de production amélioré | Disponibilité générale |
| Contrôle de la production | Un nouveau bouton Fin de pause a été ajouté à la page Terminal des bons de travail | Obligatoire |
| Contrôle de la production | [Activer la génération automatique du numéro de contenant lors de la déclaration de fin dans le périphérique de bon de travail](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Contrôle de la production | Activer la réception partielle des articles sous-traités et corrigez l’erreur de calcul du rebut pour les lignes de nomenclature de type Fournisseur | Obligatoire |
| Contrôle de la production | [Fonctionnalité de verrouillage des périphériques des bons de travail et des terminaux des bons de travail afin de procéder à leur désinfection](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Contrôle de la production | Améliorations apportées aux boîtes de dialogue d’approbation et de transfert des tâches | Obligatoire |
| Contrôle de la production | [Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Contrôle de la production | [Imprimer une étiquette à partir d’un périphérique de bons de travail](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Contrôle de la production | [Exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Obligatoire |
| Contrôle de la production | [Fonctionnalité de gestion d’actifs pour l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Activé par défaut |
| Contrôle de la production | [Recherche de tâche pour l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md) | Activé par défaut |
| Contrôle de la production | [Remplacer la réservation de production par défaut](../production-control/override-default-reservation-principle.md) | Activé par défaut |
| Contrôle de la production | [Afficher les numéros de série, de traitements par lots et de contenants complets dans l’interface d’exécution de l’atelier de production](whats-new-scm-10-0-21.md) | Activé par défaut |
| Ventes et marketing | [Amélioration des performances des commandes client](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Disponibilité générale |
| Ventes et marketing | Amélioration des performances des devis de vente | Disponibilité générale |
| Ventes et marketing | Stratégie d’exportation de données référencées de commande client | Obligatoire |
| Ventes et marketing | [Stratégie de suppression entre les lignes de commande client et lignes de commande fournisseur](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Obligatoire |
| Ventes et marketing | [Stratégie d’exportation de données référencées de devis de vente](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Obligatoire |
| Ventes et marketing | [Optimisation de l’exportation de l’entité de données des contacts](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Activé par défaut |
| Ventes et marketing | Activer la recherche pour les champs d’introduction et de conclusion du document du devis de vente | Activé par défaut |
| Ventes et marketing | [Améliorer les performances de l’état des « 100 principaux clients »](whats-new-scm-10-0-23.md) | Activé par défaut |
| Ventes et marketing | Recalculer le solde client estimé | Activé par défaut |
| Ventes et marketing | [Enregistrement de la ligne de commande client de retour avec précision décimale avec et sans poids variable](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Activé par défaut |
| Ventes et marketing | [Vues enregistrées pour les ventes et le marketing](saved-views-scm.md) | Activé par défaut |
| Ventes et marketing | Confirmation de commande client en un seul clic | Activé par défaut |
| Gestion des entrepôts | [Modèles de cross-docking avec instructions d’emplacement](../warehousing/planned-cross-docking.md) | Disponibilité générale |
| Gestion des entrepôts | [Désactiver les réceptions prévues à partir d’ordres de qualité qui échantillonnent le stock bloqué](../inventory/inventory-blocking.md) | Disponibilité générale |
| Gestion des entrepôts | Historique de réception de contenant | Disponibilité générale |
| Gestion des entrepôts | [Interface de l’équipement de manutention du matériel](../warehousing/mhax.md) | Disponibilité générale |
| Gestion des entrepôts | [Arrondir les quantités vers le bas pour l’unité de vente la plus proche à la libération dans l’entrepôt](whats-new-scm-10-0-19.md) | Disponibilité générale |
| Gestion des entrepôts | Prise en charge de l’unité d’échelle pour les listes de travail d’application d’entrepôt | Disponibilité générale |
| Gestion des entrepôts | Détails de l’étiquette de la vague d’expédition | Disponibilité générale |
| Gestion des entrepôts | [Utiliser une API plus rapide pour la clôture/réouverture des conteneurs sur la station de conditionnement](whats-new-scm-10-0-21.md) | Disponibilité générale |
| Gestion des entrepôts | [Valider les modèles sélectionnés pour les tâches de réapprovisionnement](whats-new-scm-10-0-20.md) | Disponibilité générale |
| Gestion des entrepôts | Autoriser le modèle de réapprovisionnement à utiliser le travail de réapprovisionnement immédiat existant (entre unités) | Obligatoire |
| Gestion des entrepôts | Affectation automatique des GUID à la création d’utilisateur WHS | Obligatoire |
| Gestion des entrepôts | Capture des variantes de produit et des dimensions de suivi dans l’application d’entreposage lors de la réception des articles du chargement | Obligatoire |
| Gestion des entrepôts | [Modifier le statut du stock des articles contrôlés par les dimensions de suivi](../inventory/inventory-statuses.md) | Obligatoire |
| Gestion des entrepôts | [Modifier le pool de travail sur le travail](../warehousing/change-work-pool-on-work.md) | Obligatoire |
| Gestion des entrepôts | [Poste de groupement complet](../warehousing/cluster-position-full.md) | Obligatoire |
| Gestion des entrepôts | [Fonction de groupement consolidé](../warehousing/putaway-clusters.md) | Obligatoire |
| Gestion des entrepôts | [Confirmer et transférer](../warehousing/confirm-and-transfer.md) | Obligatoire |
| Gestion des entrepôts | [Confirmer les expéditions sortantes des traitements par lots](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Obligatoire |
| Gestion des entrepôts | [Contrôler l’affichage ou non d’une page de résumé de réception sur les appareils mobiles](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obligatoire |
| Gestion des entrepôts | [Traitement différé de l’opération manuelle de mouvement de stock](../warehousing/deferred-processing-manual-inventory-movement.md) | Obligatoire |
| Gestion des entrepôts | Ne pas autoriser la création des chargements, qui ne satisfont pas aux exigences du modèle de création de chargement de vague | Obligatoire |
| Gestion des entrepôts | [Mises en page d’étiquettes de contenant améliorées](../warehousing/document-routing-layout-for-license-plates.md) | Obligatoire |
| Gestion des entrepôts | [Évaluer toutes les actions pour les directives d’emplacement qui autorise plusieurs SKU](/troubleshoot/dynamics-365/supply-chain/warehousing/evaluate-multiple-location-directive-actions) | Obligatoire |
| Gestion des entrepôts | Masquer le champ Valeur totale sur les pages « Toutes les charges » et « Détails de la charge » | Obligatoire |
| Gestion des entrepôts | Configuration de la version d’étiquette du contenant | Obligatoire |
| Gestion des entrepôts | Correction manuelle de la ligne de chargement pour les administrateurs ou les utilisateurs approuvés similaires | Obligatoire |
| Gestion des entrepôts | [Positionnement des contenants d’emplacement](../warehousing/location-license-plate-positioning.md) | Obligatoire |
| Gestion des entrepôts | [Mélange de dimensions de produit d’emplacement](../warehousing/location-product-dimension-mixing.md) | Obligatoire |
| Gestion des entrepôts | Rendre modifiable le champ Statut du stock pour les mouvements de stock sur l’appareil mobile | Obligatoire |
| Gestion des entrepôts | Service de prélèvement de ligne vente manuel pour les administrateurs ou les utilisateurs approuvés similaires | Obligatoire |
| Gestion des entrepôts | [Empêcher l’utilisation des contenants expédiés de l’ordre de transfert dans d’autres entrepôts que celui de destination](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obligatoire |
| Gestion des entrepôts | Inviter à résoudre les noms ambigus « Emplacement/Contenant » | Obligatoire |
| Gestion des entrepôts | [Contrôle qualité](../warehousing/quality-check.md) | Obligatoire |
| Gestion des entrepôts | [Paramètres utilisateur, icônes et titres des étapes pour la nouvelle application d’entrepôt](../warehousing/install-configure-warehouse-management-app.md) | Obligatoire |
| Gestion des entrepôts | [Zone d’emplacement supplémentaire](../warehousing/additional-location-zones.md) | Activé par défaut |
| Gestion des entrepôts | [Créer et traiter les ordres de transfert à partir de l’application d’entrepôt](../warehousing/create-transfer-order-from-warehouse-app.md) | Activé par défaut |
| Gestion des entrepôts | Activer le contrôle rapide pour les appareils mobiles d’entrepôt | Activé par défaut |
| Gestion des entrepôts | [Durée d’exécution maximale de la tâche de nettoyage des entrées disponibles pour la gestion des entrepôts](../warehousing/onhand-cleanup.md) | Activé par défaut |
| Gestion des entrepôts | [Visualisation de la charge de travail sortante](../warehousing/outbound-workload-visualization.md) | Activé par défaut |
| Gestion des entrepôts | [Traiter les événements d’application d’entrepôt](../warehousing/warehouse-app-events.md) | Activé par défaut |
| Gestion des entrepôts | [Vue enregistrée pour l’atelier de planification des chargements](saved-views-scm.md) | Activé par défaut |
| Gestion des entrepôts | [Vue enregistrée pour la page des détails du travail](saved-views-scm.md) | Activé par défaut |
| Gestion des entrepôts | [Vue enregistrée pour le traitement de la vague](saved-views-scm.md) | Activé par défaut |
| Gestion des entrepôts | [Vues enregistrées pour le traitement du chargement](saved-views-scm.md) | Activé par défaut |
| Gestion des entrepôts | [Vues enregistrées pour le traitement de l’expédition](saved-views-scm.md) | Activé par défaut |
| Gestion des entrepôts | [Détails du traitement par lots des vagues](../warehousing/wave-processing.md) | Activé par défaut |
| Gestion des entrepôts | [Notifications d’exécution de vague](../warehousing/wave-execution-notifications.md) | Activé par défaut |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.25 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.25 (avril 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.25, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

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

