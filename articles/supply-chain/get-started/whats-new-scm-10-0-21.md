---
title: Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.21 (octobre 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ec7fcb97bd46551846ccee13b369a1b02a589688
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075297"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.21 (octobre 2021)

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.21. Cette version a un numéro de build de 10.0.960 et est disponible comme suit :

- **Version préliminaire :** Août 2021
- **Disponibilité générale de la version (mise à jour manuelle) :** Septembre 2021
- **Disponibilité générale de la version (mise à jour automatique) :** Octobre 2021

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités comprises dans cette version. La colonne *Fonctionnalité* fournit des liens vers le [programme de publication](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), où vous pouvez voir les dates de lancement officiel de chaque fonctionnalité. La colonne *Plus d’informations* fournit plus de détails et/ou de liens vers la documentation connexe.

La plupart de ces fonctionnalités doivent être activées à l’aide de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) avant de pouvoir les utiliser.

| Fonctionnalités | Fonctionnalité | Informations supplémentaires |
|---|---|---|
| Inventaire&nbsp;et&nbsp;logistique | [Complément Comptabilité globale des stocks pour Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Page d’accueil de la comptabilité globale des stocks](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Valider les ajustements en stock à l’aide de codes de motif configurables connectés aux comptes de contrepartie](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Codes motif d’inventaire de stock](../warehousing/reason-codes-for-counting-journals.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Stratégie d’exportation de données référencées de devis de vente](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Choisissez si les modifications des données référencées par devis entraîneront l’ajout de ces devis (ou lignes) à la prochaine exportation incrémentielle. Vos exportations incrémentielles s’exécuteront plus rapidement si vous choisissez de ne pas inclure de tels devis ou lignes.<br><br>Cette fonctionnalité ajoute un paramètre appelé **Ignorer les données référencées des devis lors du suivi des modifications** sur la page **Paramètres de la Comptabilité client**. |
| Inventaire&nbsp;et&nbsp;logistique | [Appel d’offre scellé](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [Soumissions sous pli scellé les appels d’offre](../procurement/sealed-bidding.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Réservation provisoire pour le complément de visibilité des stocks](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Réservations dans la visibilité des stocks](../inventory/inventory-visibility-reservations.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Améliorations des déductions et du poids variable pour la gestion des remises](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Gérer les déductions à l’aide du workbench de déduction](../rebate-management/deduction-workbench.md )<br><br>[Traiter, examiner et valider les remises](../rebate-management/process-review-post.md)<br><br>[Accords de gestion des remises](../rebate-management/rebate-management-deals.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Instructions d’étape de l’application d’entrepôt](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Personnaliser les titres d’étapes et les instructions pour l’application mobile Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Inventaire&nbsp;et&nbsp;logistique | [Pauses de travail et suivi des mises à jour pour le coût au débarquement](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Suivi des mises à jour pour rangement](../landed-cost/update-tracking-putaway.md )<br><br>[Traitement de marchandises en transit](../landed-cost/in-transit-processing.md) |
| Planification générale | [Jours négatifs pour l’optimisation de la planification](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolérance de retard (jours négatifs)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire). Si vous souhaitez utiliser l’une de ces fonctionnalités, vous devez l’activer explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom&nbsp;de la fonctionnalité&nbsp;dans Gestion&nbsp;des fonctionnalités | Informations supplémentaires |
|---|---|---|
| Gestion des coûts | Détails de la progression de la clôture du stock | Cette fonctionnalité d’évaluation permet une vue détaillée de la progression de la clôture des stocks. |
| Approvisionnements | Empêcher la surconsommation des réservations budgétaires générales lorsque le flux de travail contient plusieurs demandes d’achat | Cette fonctionnalité d’évaluation améliore la vérification des erreurs lorsque les utilisateurs soumettent et approuvent des demandes d’achat qui dépassent le solde restant d’une ligne de réservation budgétaire générale. Cela permet d’éviter la surconsommation des réservations budgétaires générales lorsque plusieurs demandes d’achat sont dans le workflow. |
| Contrôle de la production | Afficher les numéros de série, de traitements par lots et de contenants complets dans l’interface d’exécution de l’atelier de production | Cette fonctionnalité offre une expérience améliorée pour l’affichage des listes de n° de série, n° lot et numéros de contenant dans l’interface d’exécution de l’atelier de production. L’affichage passe d’une vue de carte avec un nombre limité de caractères à une vue de liste qui offre suffisamment d’espace pour afficher les valeurs complètes. La liste offre également la possibilité de rechercher des numéros spécifiques. |
| Ventes et marketing | Limiter le nombre de commandes clients qui peuvent être sélectionnées pour validation | Cette fonctionnalité vous permet de définir le nombre maximal de commandes client pouvant être sélectionnées lors de la validation des confirmations, des prélèvements, des bons de livraison et des factures à partir de la page de liste des commandes client. Elle est activée automatiquement. Cette fonctionnalité ajoute un paramètre appelé **Nombre max. de commandes client à valider** dans la page **Paramètres de la comptabilité client**. Le nouveau paramètre prend par défaut une valeur de *100*. Cette fonctionnalité permet d’améliorer les performances de la page de liste des commandes client lorsqu’un nombre important de commandes client est sélectionné. Elle n’a aucun impact sur le nombre de commandes client pouvant être traitées par une tâche périodique. |
| Gestion des entrepôts | Découpler le travail de rangement des APE | Cette fonctionnalité est requise pour envoyer et recevoir des avis d’expédition anticipés (ASN) lorsque vous exécutez une charge de travail de gestion d’entrepôt sur une unité d’échelle (dans le cadre d’une topologie hybride distribuée). Il ajoute une nouvelle table de base de données dédiée au stockage des informations sur le travail de rangement. Auparavant, ces informations étaient stockées dans des tables également utilisées pour les ASN. |
| Gestion des entrepôts | Insérer des créneaux dans les unités mixtes | Permet au système d’insérer des articles dans des emplacements comprenant des unités mixtes (telles que des boîtes et des caisses). Pour chaque ligne de modèle de créneau, cette fonctionnalité vous permet de choisir si la ligne doit positionner les articles à des emplacements à unités mixtes ou à unité unique. |
| Gestion des entrepôts | Utiliser une API plus rapide pour la clôture/réouverture des conteneurs sur la station de conditionnement | Lorsque cette fonctionnalité d’évaluation est activée, les transactions de stock liées aux conteneurs sont créées à l’aide d’un processus léger qui améliore les performances de fermeture ou de réouverture des conteneurs lors du traitement manuel de la station d’emballage. |

## <a name="features-turned-on-by-default-in-this-release"></a>Fonctionnalités activées par défaut dans cette version

Le tableau suivant répertorie les fonctionnalités qui sont activées par défaut dans la version 10.0.21. La plupart des fonctionnalités qui ont été activées de manière atomique peuvent être désactivées dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Nom de la fonction | Date d’activation | Fonction ajoutée le | État de la fonctionnalité | Module |
| :--- | :--- | :--- | :--- | :--- |
| Stockage des états sur le stock disponible | 01/09/2021 | 01/04/2020 | Activé par défaut | Gestion des entrepôts et des stocks |
| Transférer l’annulation de commande | 01/09/2021 | 13/07/2020 | Activé par défaut | Gestion des entrepôts et des stocks |
| Déverrouiller le journal de stock | 01/09/2021 | 17/08/2020 | Activé par défaut | Gestion des entrepôts et des stocks |
| Vues enregistrées pour la gestion des stocks | 01/09/2021 | 30/09/2020 | Activé par défaut | Gestion des entrepôts et des stocks |
| Navigation jusqu’à la version de nomenclature à partir des lignes de nomenclature | 01/09/2021 | 11/11/2019 | Activé par défaut | Gestion des entrepôts et des stocks |
| Utilisation de l’unité de mesure et de la quantité d’unités dans les journaux de stock | 01/09/2021 | 11/11/2019 | Activé par défaut | Gestion des entrepôts et des stocks |
| Autoriser les valeurs d’attributs de lot vides | 01/09/2021 | 11/11/2019 | Activé par défaut | Gestion des entrepôts et des stocks |
| Incrémenter automatiquement les numéros de ligne des lignes d’ordre de transfert de stock | 01/09/2021 | 11/10/2019 | Activé par défaut | Gestion des entrepôts et des stocks |
| Workflow d’approbation du journal de stock | 01/09/2021 | 06/01/2020 | Activé par défaut | Gestion des entrepôts et des stocks |
| Activer la fonction d’avertissement des paramètres de gestion de la qualité du stock | 01/09/2021 | 07/10/2019 | Activé par défaut | Gestion des entrepôts et des stocks |
| Créer un ordre de transfert à partir de la ligne de vente | 01/09/2021 | 31/08/2019 | Activé par défaut | Gestion des entrepôts et des stocks |
| Sélection du modèle de prévision sur les détails de prévision de la demande | 01/09/2021 | 11/10/2019 | Activé par défaut | Planification générale |
| Visualisation de la progression de la planification | 01/09/2021 | 07/10/2019 | Activé par défaut | Planification générale |
| Confirmation automatique pour l’optimisation de la planification | 01/09/2021 | 11/10/2019 | Activé par défaut | Planification générale |
| Confirmation de la mise en parallèle des ordres prévisionnels | 01/09/2021 | 31/08/2019 | Activé par défaut | Planification générale |
| Message de soumission d’offre réussie | 01/09/2021 | 15/05/2019 | Activé par défaut | Approvisionnements |
| Lien de référence de l’appel d’offre ajouté à la CF | 01/09/2021 | 31/08/2019 | Activé par défaut | Approvisionnements |
| Possibilité de confirmer les commandes fournisseur acceptées de la collaboration fournisseur par lots | 01/09/2021 | 10/09/2019 | Activé par défaut | Approvisionnements |
| Améliorations des cXML d’achat | 01/09/2021 | 11/11/2019 | Activé par défaut | Approvisionnements |
| Afficher le lien &quot;Ouvrir les appels d’offres publiés&quot; sous forme de vignette | 01/09/2021 | 30/09/2020 | Activé par défaut | Approvisionnements |
| Questions et réponses concernant les appels d’offre | 01/09/2021 | 19/02/2020 | Activé par défaut | Approvisionnements |
| Documents d’expédition et informations sur les matières dangereuses d’un produit | 01/09/2021 | 14/06/2020 | Activé par défaut | Gestion des informations sur les produits |
| Contrôle stricte des quantités de commande par défaut | 01/09/2021 | 24/06/2020 | Activé par défaut | Gestion des informations sur les produits |
| Fonction de gestion du pays d’origine | 01/09/2021 | 13/07/2020 | Activé par défaut | Gestion des informations sur les produits |
| Vues enregistrées pour les produits lancés | 01/09/2021 | 30/09/2020 | Activé par défaut | Gestion des informations sur les produits |
| Améliorations apportées aux boîtes de dialogue d’approbation et de transfert des tâches | 01/09/2021 | 11/10/2019 | Activé par défaut | Contrôle de la production |
| Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail | 01/09/2021 | 31/08/2019 | Activé par défaut | Contrôle de la production |
| Un nouveau bouton Fin de pause a été ajouté à la page Terminal des bons de travail | 01/09/2021 | 19/02/2020 | Activé par défaut | Contrôle de la production |
| Activez la réception partielle des articles sous-traités et corrigez l’erreur de calcul du rebut pour les lignes de nomenclature de type Fournisseur. | 01/09/2021 | 11/11/2019 | Activé par défaut | Contrôle de la production |
| Vues enregistrées pour le contrôle de la production | 01/09/2021 | 17/08/2020 | Activé par défaut | Contrôle de la production |
| Dynamics 365 Guides pour la Fabrication | 01/09/2021 | 13/07/2020 | Activé par défaut | Contrôle de la production |
| Exécution de l’atelier de production | 01/09/2021 | 30/09/2020 | Activé par défaut | Contrôle de la production |
| Fonctionnalité de verrouillage des périphériques des bons de travail et des terminaux des bons de travail afin de procéder à leur désinfection | 01/09/2021 | 10/05/2020 | Activé par défaut | Contrôle de la production |
| Répartition des frais sur une commande client | 01/09/2021 | 30/09/2020 | Activé par défaut | Ventes et marketing |
| Limiter le nombre de commandes clients qui peuvent être sélectionnées pour validation | 01/09/2021 | 01/09/2021 | Activé par défaut | Ventes et marketing |
| Nettoyer l’historique des mises à jour des commandes clients | 01/09/2021 | 01/09/2021 | Activé par défaut | Ventes et marketing |
| Modifier la souche de numéros pour le travail d’inventaire tournant | 01/09/2021 | 07/10/2019 | Activé par défaut | Gestion des entrepôts |
| Réapprovisionnement d’une demande de vague basée sur la tâche | 01/09/2021 | 07/10/2019 | Obligatoire | Gestion des entrepôts |
| Masquer le champ Valeur totale sur les pages &quot;Toutes les charges&quot; et &quot;Détails de la charge&quot; | 01/09/2021 | 07/10/2019 | Activé par défaut | Gestion des entrepôts |
| Impression d’étiquettes de vague | 01/09/2021 | 19/02/2020 | Obligatoire | Gestion des entrepôts |
| Associer les mouvements de stock de commande fournisseur au chargement | 01/09/2021 | 06/01/2020 | Obligatoire | Gestion des entrepôts |
| Mises en page d’étiquettes de contenant améliorées | 01/09/2021 | 19/02/2020 | Activé par défaut | Gestion des entrepôts |
| Blocage des tâches à l’échelle de l’organisation | 01/09/2021 | 19/02/2020 | Obligatoire | Gestion des entrepôts |
| Détails de la ligne de travail | 01/09/2021 | 11/10/2019 | Activé par défaut | Gestion des entrepôts |
| Rendre modifiable le champ Statut du stock pour les mouvements de stock sur l’appareil mobile | 01/09/2021 | 16/10/2019 | Activé par défaut | Gestion des entrepôts |
| Confirmer les expéditions sortantes des traitements par lots | 01/09/2021 | 13/07/2020 | Activé par défaut | Gestion des entrepôts |
| Contrôler l’affichage ou non d’une page de résumé de réception sur les appareils mobiles | 01/09/2021 | 01/04/2020 | Activé par défaut | Gestion des entrepôts |
| Inviter à résoudre les noms ambigus &#39;Loc / LP&#39; | 01/09/2021 | 01/04/2020 | Activé par défaut | Gestion des entrepôts |
| Capture des variantes de produit et des dimensions de suivi dans l’application d’entreposage lors de la réception des articles du chargement | 01/09/2021 | 10/05/2020 | Activé par défaut | Gestion des entrepôts |
| N’autorisez pas à créer des chargements, qui ne satisfont pas aux exigences du modèle de création de chargement de vague. | 01/09/2021 | 17/08/2020 | Activé par défaut | Gestion des entrepôts |
| Évaluer toutes les actions pour les directives d’emplacement qui autorise plusieurs SKU | 01/09/2021 | 30/09/2020 | Activé par défaut | Gestion des entrepôts |

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

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finances et Opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.21 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications Finances et Opérations, version 10.0.21 (octobre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

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
