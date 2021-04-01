---
title: Vue d’ensemble du processus de fabrication
description: Cette rubrique donne une vue d’ensemble des processus de production. Il décrit les différents stades des ordres de fabrication, des lots de commandes et des kanbans, de la création à la clôture de la période financière.
author: cvocph
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace, ProdParmCostEstimation, ProdParmRelease, ProdSchedule, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19832
ms.assetid: 0e83c7ea-feba-4ed6-8717-8b48a3b8804a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12780fc1fa9f6a9c25495ace34b9731df49d5ae6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209417"
---
# <a name="production-process-overview"></a>Vue d’ensemble du processus de fabrication

[!include [banner](../includes/banner.md)]

Cette rubrique donne une vue d’ensemble des processus de production. Il décrit les différents stades des ordres de fabrication, des lots de commandes et des kanbans, de la création à la clôture de la période financière. 

La production de produits, un processus également appelé cycle de vie de la production, suit des étapes spécifiques nécessaires pour terminer la fabrication d’un article. Le cycle de vie commence avec la création de l’ordre de fabrication, du lot de commandes, ou du kanban. Il commence par la création de l’ordre de fabrication et se termine par un produit fini, fabriqué et prêt pour le client ou une autre phase de production. Chaque étape du cycle de vie requiert différents types d’informations pour l’exécution du processus. Lorsque chaque étape est terminée, l’ordre de fabrication, le lot de commandes ou le kanban l’indique en modifiant son statut de production. Les différents types de produits requièrent différents processus de fabrication.  

Le module **Contrôle de la production** est lié à d’autres modules, tel que **Gestion des informations sur les produits** **Gestion des stocks**, **Comptabilité**, **Gestion des entrepôts**, **Comptabilité de projet** et **Administration d’organisation**. Cette intégration prend en charge le flux d’informations nécessaire pour exécuter le processus de fabrication d’un article fini.  

Le processus de production est généralement influencé par les méthodes d’évaluation des stocks et de contrôle de gestion choisies pour un processus de production spécifique. Supply Chain Management prend en charge à la fois le coût réel (premier entré, premier sorti \[FIFO\] ; dernier entré, premier sorti \[LIFO\] ; moyenne de déplacement ; moyenne pondérée périodique) et les méthodes de coût standard. Le lean manufacturing (production au plus juste) est mis en œuvre selon le principe de la comptabilité à rebours.  

Le choix des méthodes de mesure des coûts définit également les besoins pour créer des rapports sur la consommation des matières et des ressources lors du processus de production. Généralement, les méthodes de coût réel exigent des rapports précis sur le niveau de tâche, tandis que les méthodes d’évaluation des coûts périodique permettent des rapports moins précis de la consommation des matières et des ressources.

## <a name="mixed-mode-manufacturing"></a>Production en mode mixte
Les différents produits et différentes topologies de production exigent l’application de différents types de commande. Supply Chain Management peut appliquer les différents types de commandes en mode mixte. Autrement dit, tous les types de commande peuvent survenir pendant le processus de bout en bout de production d’un produit fini.

-   **Ordre de fabrication** – Il s’agit du type de commande classique pour produire un produit ou une variante de produit spécifique dans une quantité donnée à une date spécifique. Les ordres de fabrication sont basés sur les nomenclatures et les gammes.
-   **Lot de commandes** – Ce type de commande est utilisé pour les secteurs de traitement et les processus distincts où la conversion de fabrication est basée sur une formule ou lorsque les coproduits et les sous-produits peuvent être des produits finis, soit en plus de, soit à la place du produit principal. Les lots de commande utilisent les nomenclatures et les gammes de type **Formule**.
-   **Kanban** – Des kanbans sont utilisés pour signaler les processus répétitifs de lean manufacturing basés sur les flux de production, les règles de kanban et les nomenclatures.
-   **Projet** – Un projet de fabrication associe des produits et services à un programme et à un budget donnés. La partie de fabrication d’un projet peut être fournie via l’un des autres types de commandes.

## <a name="manufacturing-principles"></a>Principes de fabrication
Pour sélectionner le principe de fabrication qui s’applique le mieux à une produit spécifique et au marché correspondant, vous devez tenir compte des exigences de production et de logistique, ainsi que des attentes des clients en termes de livraison dans les délais.

-   **Production sur stock** – Il s’agit du principe classique de fabrication, où les produits sont fabriqués pour le stock, selon les prévisions ou le rechargement de stock minimal (ce dernier est généralement calculé en fonction de la prévision ou de la consommation historique).
-   **Production à la commande** – Les produits standard sont fabriqués ou finis sur commande. Bien que la préproduction puisse être effectuée à l’aide du principe Créer le stock, de coûteuses étapes de la chaîne de valeur, ou des étapes qui créent des variantes, sont déclenchées par une commande client ou un ordre de transfert.
-   **Configuration à la commande** – À l’instar du principe de Production à la commande, les opérations finales de la chaîne de valeur sont fabriquées sur commande. La variante de produit réelle fabriquée n’est pas prédéfinie, mais est créée au moment de la saisie de commande, selon le modèle de configuration du produit de vente. Le principe de Configuration à la commande exige un certain niveau d’unification du processus pour une gamme de produits donnée.
-   **Conception à la commande** – Les processus de type « Conception à la commande » sont généralement traités par un projet et commencent habituellement par la phase d’ingénierie. Lors de la phase d’ingénierie, les produits réels nécessaires pour satisfaire la commande sont conçus et décrits. Les ordres de fabrication, les lots de commandes, ou les kanbans peuvent ensuite être créés pour fabriquer les produits.

## <a name="overview-of-the-production-life-cycle"></a>Présentation du cycle de vie de production
Les étapes suivantes dans le cycle de vie de la production peuvent se produire pour tous les types de commandes de fabrication en mode mixte. Toutefois, pas tous sont représentés comme statut d’ordre significatif.

1.  **Créé** – Permet de créer un ordre de fabrication, un lot de commandes, ou un kanban manuellement, ou vous pouvez configurer le système pour les générer en fonction de divers signaux de demande. La planification crée des ordres de fabrication, des lots de commandes, ou des kanbans lors de la confirmation d’ordres prévisionnels. D’autres signaux de demande sont des commandes client ou des signaux d’approvisionnement invariable à partir d’autres ordres de fabrication ou kanbans. Pour les kanbans de quantité fixe, des signaux de demande sont générés lorsque des kanbans sont enregistrés comme vides.
2.  **Estimé** – Permet de calculer des estimations pour les matières et la consommation de ressources. L’estimation génère des transactions de stock pour les matières premières ayant un statut **En commande**. Les réceptions des produits, coproduits et sous-produits principaux sont générées lorsque des ordres de fabrication ou des lots de commandes sont estimés. Si la nomenclature contient des lignes de type **Approvisionnement invariable**, les commandes fournisseur pour les matières ou les services d’opérations sous-traitées sont générés et invariables par rapport à l’ordre de fabrication ou au lot de commandes. Les articles ou les commandes sont réservés selon la stratégie de réservation de l’ordre de fabrication, et le prix des produits finis est calculé en fonction des paramètres.
3.  **Programmé** – Vous pouvez programmer la production sur la base d’opérations, de tâches individuelles ou les deux.
    -   **Ordonnancement** – Ce mode de planification permet de définir un programme approximatif à long terme. Grâce à cette méthode, vous pouvez affecter des dates de début et de fin aux ordres de fabrication. Si les ordres de fabrication sont liés à des opérations de gamme, vous pouvez les affecter à des groupes de centres de coût.
    -   **Planification de tâche** – Ce mode de planification permet de définir un programme détaillé. Chaque opération est divisée en tâches individuelles avec des dates, des heures et des ressources opérationnelles affectées. Si la capacité finie est utilisée, les tâches sont affectées à des ressources opérationnelles en fonction de leur disponibilité. Vous pouvez afficher et modifier le programme dans un diagramme de Gantt.
    -   **Programme Kanban** – Les tâches de kanban sont planifiées dans le tableau de planification kanban ou automatiquement planifiées en fonction de la configuration automatique des règles de kanban.

4.  **Lancé** – Permet de lancer l’ordre de fabrication ou un lot de commandes lorsque le programme est terminé et lorsque les matières sont disponibles pour être prélevées ou préparées. Le contrôle de disponibilité des matières aide le superviseur de l’atelier à évaluer la disponibilité des matières pour les ordres de fabrication ou les lots de commandes. Vous pouvez également imprimer des documents d’ordre de fabrication, tels que des listes de prélèvement, un bon de travail, une fiche production et une tâche de gamme. Une fois l’ordre de fabrication lancé, le statut de l’ordre change pour indiquer que la fabrication peut commencer. Lorsque la gestion de l’entrepôt est utilisée, le lancement de l’ordre de fabrication ou le lot de commandes publie les lignes de nomenclature de production à la gestion de l’entrepôt. Des vagues d’entrepôt et le travail d’entrepôt sont ensuite générés selon la configuration de l’entrepôt.
5.  **Préparé**/**Prélevé** – Lorsque toutes les matières et ressources ont été acheminées jusqu’à l’emplacement de production, les lignes de nomenclature de production ou les lignes de kanban sont mises à jour avec le statut **Prélevé**. Les commandes d’approvisionnement invariable et le travail d’entrepôt correspondant sont généralement effectués à ce moment précis. Les cartes kanban ou bons de travail nécessaires pour signaler la progression de la production doivent être attribués et imprimés.
6.  **Commencé** – Lorsqu’un ordre de fabrication, un lot de commandes, ou un kanban est lancé, vous pouvez déclarer la consommation de matières et de ressources par rapport à la commande. Le système peut être configuré pour valider automatiquement la consommation des matières et des ressources affectées à la commande lorsque la commande est commencée. Cette répartition est appelée préconsommation, effacement estimé ou autoconsommation. Vous pouvez attribuer manuellement des matières aux ordres de fabrication ou lots de commandes en créant des journaux de prélèvements supplémentaires. Vous pouvez également affecter manuellement le travail et d’autres coûts de gamme à la commande. Si vous utilisez l’ordonnancement, vous pouvez affecter ces coûts en créant un journal des fiches productions. Si vous utilisez la planification de tâches, vous pouvez affecter ces coûts en créant un journal des bons de travail. Les ordres de fabrication ou lots de commandes peuvent être commencés en lots de quantité finale requise. Dans un ordre de fabrication, le lot de commandes ou le kanban, les tâches créées peuvent être démarrées et déclarées séparément via les journaux, le terminal externe de contrôle de suivi de la production ou les tableaux kanban.
7.  Connaître l’état de progression/Tâches **terminées** – Permet d’utiliser le terminal de contrôle de suivi de la production, les journaux de production, les tableaux kanban, ou les utilitaires de numérisation mobile pour déclarer la progression de production par tâche ou ressource. La consommation des matières et des ressources est validée et le statut des kanbans, ordres de fabrication et lots de commandes correspondants peut être mis à jour avec **Reçu** ou **Déclaré terminé**. Le travail de rangement pour l’entrepôt peut être créé en fonction de la configuration de l’entrepôt.
8.  **Déclaré terminé** (accusé de réception de marchandises) – Lorsqu’un ordre de fabrication ou un lot de commandes est déclaré terminé, la quantité des produits finis déclarés terminés est mise à jour dans le stock. Cette quantité inclut la quantité de coproduits et de sous-produits appropriés. Si vous utilisez la gestion des travaux en cours, un journal comptable est établi pour réduire les comptes de travaux en cours et augmenter le stock de produits finis. Lorsque le coût d’un ordre de fabrication est calculé, le coût réel de la production est validé. Si les coûts de matières et main d’œuvre associés à la fabrication ne sont pas encore répartis dans un journal ou par préconsommation, vous pouvez les répartir automatiquement par post-consommation. La répartition via la post-consommation implique la post-déduction des processus de mouvement de stock. Si l’ordre de fabrication est terminé, sélectionnez la case à cocher **Tâche de fin** pour modifier le statut restant sur **Terminé**. Sinon, laissez le champ vide pour autoriser la déclaration des quantités supplémentaires produites.
9.  **Évaluation de la qualité** – Un accusé de réception de marchandises peut déclencher la création des ordres de qualité, en fonction de la configuration des processus de test et des règles de qualité définis pour des produits spécifiques. Parce qu’un ordre de qualité peut mettre à jour le statut du stock ou les attributs de lot des produits testés, l’évaluation de la qualité est un processus obligatoire de nombreux secteurs.
10. **Rangement** et **Commande à expédier** – Après l’accusé de réception de marchandises et l’évaluation de la qualité, le travail de rangement dirige les produits reçus vers le point de consommation suivant, vers un entrepôt de produits finis ou vers une zone d’expédition s’il s’agit de commandes à expédier.
11. **Terminé** – Avant la fin de la production, les coûts réels sont calculés pour la quantité produite. Tous les coûts estimés de matière, main d’œuvre et frais généraux sont contrepassés et remplacés par les coûts réels. Si vous sélectionnez la case à cocher **Tâche de fin** lors du calcul des coûts, le statut de l’ordre de fabrication passe à **Terminé**. Ce statut empêche que tout coût supplémentaire soit validé dans un ordre de fabrication terminé.
12. **Clôture de période** – Certains principes de contrôle de gestion, tels que la moyenne périodique, le coût de post-consommation, FIFO ou LIFO, exigent que les activités périodiques clôturent la période du stock ou financière. En général, le système essaie de déclarer la consommation de toutes les matières et de toutes les ressources, ainsi que les corrections du stock et la mise au rebut, avant la clôture des périodes. Cette déclaration est généralement effectuée à l’aide de journaux de mouvements de stock ou des journaux d’ajustement. L’objectif consiste à évaluer la performance économique des unités opérationnelles par période. Dans certains cas, lorsque les ordres de fabrication à long terme sont utilisés couvrant les périodes des états financiers, les journaux de production sont utilisés pour déclarer la progression de la production et la consommation des ressources d’ici à la fin de la période.


<a name="additional-resources"></a>Ressources supplémentaires
--------

[Rétroaction de production](production-feedback.md)

[Vue d’ensemble des modèles de configuration de produit](../pim/product-configuration-models.md)

[Vue d’ensemble du Lean manufacturing](lean-manufacturing-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]