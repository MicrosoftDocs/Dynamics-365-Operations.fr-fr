---
title: "Calcul des coûts de post-consommation"
description: "Cette rubrique présente le concept de comptabilité à rebours utilisé pour la production au plus juste."
author: YuyuScheller
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: conradv
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: e520c292b7350f332649f23fb4232e7ecd191776
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017


---

# <a name="backflush-costing"></a>Calcul des coûts de post-consommation

[!include[banner](../includes/banner.md)]


Cette rubrique présente le concept de comptabilité à rebours utilisé pour la production au plus juste. 

L'évaluation des coûts de production au plus juste permet au flux de production d'utiliser la méthode de formation des coûts qui est appelée comptabilité à rebours. Dans la méthode de comptabilité à rebours, les matières directes qui sont consommées sont cumulées dans le compte de coût de (WIP) des travaux en cours du flux de production. Le groupe de modèles de stock pour les coûts standard est utilisé. Les produits reçus du flux de production sont déduits des travaux en cours à leur coût standard. La différence principale entre la comptabilité à rebours et le coût standard est que, pour la comptabilité à rebours, les écarts ne sont pas calculés par kanban ou produit fini. Au lieu de cela, les écarts sont calculés par flux de production au cours d'une période. Cette méthode offre une véritable méthode de production au plus juste pour déclarer la consommation de matières. Les quantités de matières prélevées dédiées ne sont pas signalées à un kanban ou un ordre de fabrication. Au lieu de cela, les lots complets ou les unités de manutention sont présentés au flux de production. Une fois les lots ou les unités de manutention enregistrés comme vides, ils sont déclarés consommés. La consommation avancée peut être utilisée, selon la [configuration du flux de production](http://ax.help.dynamics.com/en/wiki/lean-manufacturing-modeling-the-lean-organization/). Avant que la consommation avancée puisse être utilisé, les organisations doivent autoriser la disparition des matières dans les travaux en cours du flux de production. La comptabilité à rebours périodique détermine la valeur effective des travaux en cours à la fin de la période. Cette détermination est basée sur les unités de manutention de kanban et le statut d'opération kanban. Les écarts entre les valeurs effectives et les valeurs réelles des travaux en cours par groupe de coûts et article sont pris en compte et affichés comme des écarts.

## <a name="configuring-backflush-costing"></a>Configuration de la comptabilité à rebours
Pour activer l'évaluation des coûts, vous définir le paramétrage suivant :

-   **Configurer les comptes des travaux en cours pour le groupe de production et le flux de production.** Les travaux en cours pour le flux de production sont spécifiés dans le groupe de production. Le flux de production de comptabilité à rebours calcule les écarts comme la différence de valeur des travaux en cours avant et après que la comptabilité à rebours soit exécutée pour chaque flux de production. Par conséquent, nous vous recommandons de créer des travaux en cours pour chaque flux de production.
-   **Affectez une catégorie de coûts au groupe de ressources.** Vous devez affecter une catégorie de coûts à la catégorie d'exécution de la cellule de travail. Pour déterminer les écarts par activité, vous devez créer une catégorie de coûts pour chaque cellule de travail. Les catégories de coûts pour le paramétrage et la quantité ne sont pas prises en compte pour l'évaluation des coûts de production au plus juste. Les comptes de travaux en cours par groupe de ressources sont ignorés dans la comptabilité à rebours. Pour les activités sous-traitées, aucune catégorie de coûts n'est requise. Le groupe de coûts affecté au service actif est utilisé à la place.
-   **Affectez les groupes de coûts.** Pour activer la segmentation de la contribution de coût dans un flux de production, vous devez affecter des groupes de coûts par type de groupe de coûts :
    -   **Groupe de coûts de matériel direct** - Le matériel direct requiert un groupe de coûts qui identifie la catégorie de matériel pour l'évaluation des coûts. Ce groupe de coûts active une vue regroupée du coût, des travaux en cours et des écarts par matériel direct.
    -   **Groupe de coûts de fabrication directe** - Le groupe de coûts de fabrication directe capture la contribution directe du coût des ressources opérationnelles au flux de production. Ce groupe de coûts active une vue regroupée du coût, des travaux en cours et des écarts par coût de fabrication.
    -   **Groupe de coûts indirects** - Le groupe de coûts indirects est requis pour calculer la contribution du coût indirect au flux de production. Ce groupe de coûts active une vue regroupée du coût, des travaux en cours et des écarts par coût indirect.
    -   **Groupe de coûts d'externalisation directe** - Le groupe de coûts pour les services active une vue regroupée du coût affecté et des travaux en cours, et détermine les écarts de coûts des services sous-traités.
    -   **Groupe de coûts pour un produit fini** - Les produits finis nécessitent un groupe de coûts qui identifie la catégorie de produit pour l'évaluation des coûts. Ce groupe de coûts active une vue regroupée du coût, des travaux en cours et des écarts par catégorie de produits. Le coût standard pour les produits est calculé à l'aide du coût basé sur la nomenclature (BOM), et des règles de flux de production et de kanban ou de la gamme.

### <a name="costing-sheet"></a>Feuille de coûts

La feuille de coûts modèle la structure de coût pour la société et est générée par les groupes de coûts pour classifier le coût. La feuille de coûts possède des écrans individuels. Elle affiche les informations sur les coûts selon la structure utilisée. Dans la feuille de coûts, vous définissez également la formule utilisée pour calculer le coût indirect. La formule de calcul peut être basée sur les quantités, le poids, le volume, ou la valeur.

-   **Définissez une version d'évaluation des coûts.** Dans la version d'évaluation des coûts, la société définit la manière dont le coût doit être mis à jour. Une version d'évaluation de coûts peut contenir une série d'enregistrements de coûts standard ou une série d'enregistrements de coûts planifiés en fonction du type d'évaluation des coûts qui lui est attribué. La version d'évaluation des coûts utilisée pour évaluer le coût de production au plus juste doit être basée sur un coût standard.
-   **Attribuez un groupe de modèles de stock pour les produits lancés.** Tous les produits liés au flux de production doivent être affectés à un groupe de modèles de stock qui utilise le groupe de modèles de stock **Coût standard**. Le coût standard est conservé par date de site et d'activation. Pour les produits génériques, le groupe de modèles de stock peut être sélectionné si le coût est conservé par variante ou produit générique.
-   **Par définition, les services sous-traités sont des services non inventoriés.** Les activités sous-traitées n'ont aucun groupe de modèles de stock. Pour évaluer les coûts d'une activité sous-traitée correctement, vous devez vous assurer que l'activité de service appartient à un groupe de modèles de stock dont la stratégie de stock est définie sur **Produit stocké = faux**.

Pour les articles de sortie, le calcul du coût basé sur le flux de production requiert qu'un coût standard soit donné pour les services liés aux activités sous-traitées. Le groupe de coûts affecté aux services permet de déterminer les écarts de coûts de l'activité sous-traitée.

## <a name="cost-calculation-for-lean-manufacturing"></a>Calcul du coût de production au plus juste
Pour les produits fournis hors du flux de production, le calcul de nomenclature doit être basée sur une version de gamme ou un flux de production. Le calcul de nomenclature calcule le coût d'un produit et la répartition associée aux ressources et aux matières nécessaires afin de créer le produit. La déduction des travaux en cours pour le flux de production est effectuée à l'aide de l'affectation d'un produit par article et par groupe de coûts.

### <a name="calculation-that-is-based-on-the-production-flow"></a>Calcul basé sur le flux de production

La production au plus juste de Microsoft Dynamics 365 for Finance and Operations est indépendante des gammes. Le calcul des coûts pour les produits provenant d'un flux de production peut être basé sur le flux de production proprement dit. Avant que le calcul soit effectué, vous devez créer une règle de kanban qui fournit le produit hors du flux de production. Si un produit peut être fourni par plusieurs flux de production au même site à la date du calcul, vous pouvez sélectionner le flux de production pour le calcul de nomenclature. Dans la page **Flux de production par défaut**, vous pouvez configurer un flux de production par défaut pour chaque article. Si plusieurs règles de kanban existent pour le même produit dans le même flux de production actif à la date du calcul, le calcul sélectionne la première règle de kanban qui est active pour le calcul.

### <a name="calculation-that-is-based-on-the-route"></a>Calcul basé sur la gamme

Le calcul basé sur une gamme est tout aussi valide que le calcul basé sur un flux de production. Toutefois, le calcul basé sur une gamme n'utilise pas l'évaluation des coûts pour la fonctionnalité de production au plus juste. La gamme doit utiliser des demandes de ressources pour les groupes de ressources. Pour éviter les écarts systématiques, elle doit également utiliser les mêmes cellules de travail, ou au moins les mêmes catégories de coûts. Là aussi, vous devez éviter les catégories de coûts pour le paramétrage et la quantité. Elles ne permettent pas de calculer le coût selon une allocation plus granulaire que la post-consommation des coûts de la production au plus juste. Pour déterminer quelle option (flux de production ou gamme) utiliser pour calculer le coût, examinez les résultats de l'analyse des coûts. La version la plus proche de la réalité et qui génère le moins d'écarts est l'option à privilégier. Dans un environnement de production au plus juste, lorsqu'un produit est fourni par un flux de production unique et une règle de kanban unique, le calcul qui est basé sur le flux de production est probablement le plus précis. Pour un article pouvant être fourni par la production au plus juste et des ordres de fabrication dans le même site, ou qui peut avoir plusieurs flux de production ou plusieurs règles de kanban dans le même flux, le calcul sera plus précis s'il se base sur une version de gamme créée spécialement pour le calcul des coûts, pas pour la production. Le calcul du flux de production doit être utilisé pour calculer les produits inclus dans la sous-traitance. Dans Microsoft Dynamics 365 for Finance and Operations, les modèles de coût pour la sous-traitance via des ordres de fabrication et pour la sous-traitance dans la structure Production au plus juste utilisent deux approches. Le production au plus juste présente un nouveau type de groupe de coûts, **Externalisation directe**, pour calculer les services sous-traités.

## <a name="material-consumption"></a>Consommation de matières
Lorsque le matériel est consommé à partir du stock vers les travaux en cours, le coût de la matière est ajouté aux travaux en cours à son coût standard réel pour un groupe de coûts. Cette opération est effectuée dans les cas suivants :

-   Les sorties de kanban sont validées pour les lignes de prélèvement de kanban qui mettent à jour le stock.
-   Les tâches de transfert sont complétées et mettent à jour le stock au prélèvement mais pas à la réception (transfert de matériel à partir du stock vers les travaux en cours).

## <a name="receiving-products-from-the-production-flow"></a>Réception de produits du flux de production
Les produits sont réceptionnés du flux de production dans les cas suivants :

-   Les tâches de traitement sont complétées et le **Stock mis à jour à la réception** est défini sur **Activé**.
-   Les tâches de traitement sont complétées et mettent à jour le stock à la réception, mais présentent un **Stock mis à jour au prélèvement** défini sur **Non** (transfert à partir des travaux en cours vers le stock). Cette option vous permet de recevoir tous les produits en dehors de flux de production indépendamment de la nomenclature et de la configuration de la gamme. Le processus suit simplement les flux physiques. Cette option est particulièrement utile pour recevoir des sous-produits, des co-produits, ou des rebuts en dehors d'un flux de production, et corriger le solde de coût des travaux en cours du flux de production en conséquence.

Les produits reçus du flux de production sont déduits des travaux en cours.

## <a name="products-in-wip"></a>Produits dans les travaux en cours
Le modèle de travaux en cours de la production au plus juste dans Microsoft Dynamics 365 for Finance and Operations vous permet d'utiliser le statut d'unité de manutention de kanban pour gérer les matières, les produits semi-finis, et les produits finis qui font partie des travaux en cours.

-   **Affecté** - Le kanban peut avoir consommé les matières qui sont comptabilisées dans les travaux en cours.
-   **Reçu** - Si le kanban fait référence à une dernière activité où le **Stock mis à jour à la réception** est défini sur **Non**, cela représente une unité de manutention totale d'un produit ou d'un produit semi-fini non enregistré en stock.

Notez que les matières dans les travaux en cours ne sont pas visibles dans les vues d'ensemble du stock disponible. Toutefois, elles sont visibles dans les vues d'ensemble de la quantité de kanban.

## <a name="consuming-products-in-wip"></a>Consommer des produits dans les travaux en cours
Les produits dans les travaux en cours sont consommés lorsque les unités de manutention de kanban correspondantes sont purgées. Un signal de kanban vide ne produit pas une transaction d'évaluation des coûts active mais sera appliqué lors de l'exécution de la prochaine comptabilité à rebours. Les unités de manutention de kanban purgées ne sont plus comptabilisées comme disponibles et sont donc calculées comme consommées dans la période.

### <a name="automatic-empty-registration"></a>Enregistrement vide automatique

Les kanbans prévus ou d'événement peuvent être paramétrés sur l'enregistrement vide automatique dans la règle de kanban :

-   **Lors de la réception des unités de manutention** - Par défaut, pour les kanbans planifiés, les matières sont déclarées comme étant consommées lorsque la dernière opération kanban est terminée. Pour les kanbans de quantité fixe, cette option est recommandée uniquement pour les kanbans avec une seule corbeille, car elle retourne la carte à la source de la demande lorsqu'un kanban est reçu à la destination finale.
-   **Lorsque la demande source est enregistrée** - Cette option n'est disponible que pour les kanbans d'événement et est l'option par défaut pour ces kanbans. Pour les travaux en cours, cette option est utile pour conserver des travaux en cours nets, car les kanbans des composants des travaux en cours sont automatiquement vidés, et donc consommés à partir des travaux en cours, lorsque le kanban parent est préparé.

Enfin, des unités de manutention de kanban peuvent être affectées (= dans le processus), reçues (= totalement), ou purgées. Il n'existe pas de purge partielle. Par conséquent, pour enregistrer précisément la consommation, il est important que vous limitiez les quantités de produits d'un kanban afin qu'elles soient inférieures à la consommation par période. Les produits qui sont déplacés vers l'atelier par gros lots couvrant plusieurs jours ou semaines de demande ne doivent pas être consommés par les travaux en cours. Au lieu de cela, ces produits doivent être conservés dans le stock.

## <a name="backflush-costing"></a>Calcul des coûts de post-consommation
Vous devez exécuter la comptabilité à rebours régulièrement pour évaluer les travaux en cours et pour produire un statut de clôture de période qui calcule les écarts de matières, main-d'œuvre, et coûts indirects. Les écarts calculés sont validés dans les comptes d'écart. Dans le processus de comptabilité à rebours, tous les flux de production de l'entité juridique sont utilisés dans la même exécution du traitement par lots. Lorsque la comptabilité à rebours s'effectue dans un lot, le traitement peut subir une exécution multithread lancée par le flux de production. La période à rebours est définie par une date de fin. Vous ne pouvez pas valider de nouvelles transactions pour une date lorsqu'un calcul de comptabilité à rebours a été exécuté. Vous ne devez jamais exécuter la comptabilité à rebours pour la date actuelle avant la fin de la journée. La comptabilité à rebours exécute les opérations suivantes.

1.  Déterminer les quantités non utilisées dans le flux de production à la date de fin de la période. Une fois la comptabilité à rebours exécutée, vous pouvez afficher les quantités inutilisées à la date d'évaluation des coûts exécutée dans la boîte de dialogue **Quantités inutilisées**.
2.  Calculer l'utilisation réelle nette du flux de production sur la période.
3.  Désactiver les travaux en cours dans la consommation réelle de ressources et de produits.
4.  Calculer les écarts de production en fonction du coût standard pour la période. **Pour les composants utilisés pour la période :**
    -   Mettre financièrement à jour les quantités réelles nettes de matériel que le flux de production a consommées sur la période. Le système traite les mouvements de stock individuels selon le principe du premier entré, premier sorti (FIFO) pour mettre à jour au niveau financier les transactions mises à jour physiquement pour le flux de production, jusqu'à ce que les quantités réelles nettes de la période soient atteintes.
    -   Les transactions sont financièrement fractionnées pour remapper les quantités consommées précises.
    -   Les quantités non utilisées dans les travaux en cours du flux de production restent avec le statut mis à jour physiquement.

    **Pour les quantités dont la production est terminée pour la période :**
    -   Mettre à jour au niveau financier les mouvements de stock pour les quantités terminées de la période.

    **Pour la conversion de coûts :**
    -   Les transactions de coûts de conversion appliquées (transactions de gamme) qui ont été enregistrées pour la période sont mises à jour financièrement.
    -   Tout coût direct de fabrication est mis à jour financièrement. Toutes les tâches de traitement de kanban terminées au cours de la période sont accumulées.
    -   Tous les coûts indirects calculés pour le matériel consommé dans la période sont calculés et déduits des travaux en cours. Le coût indirect restant est validé comme écart.

5.  Calculer les écarts de production en fonction du coût standard. L'écart est calculé par groupe de coûts.






