---
title: "Groupes de coûts"
description: "Les groupes de coûts servent de base pour la segmentation et l'analyse des contributions de coûts dans le coût calculé d'un article fabriqué, telles que les contributions de coûts pour les matériaux, la main-d'œuvre et les frais généraux. La segmentation des groupes de coûts a plusieurs synonymes dans les environnements de fabrication, comme répartition des coûts, décomposition des coûts ou classification des coûts."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCostGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 022cca99bc5ad1f4c023b0b7aba748a2ef6b1d60
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="cost-groups"></a>Groupes de coûts

[!include[banner](../includes/banner.md)]


Les groupes de coûts servent de base pour la segmentation et l'analyse des contributions de coûts dans le coût calculé d'un article fabriqué, telles que les contributions de coûts pour les matériaux, la main-d'œuvre et les frais généraux. La segmentation des groupes de coûts a plusieurs synonymes dans les environnements de fabrication, comme répartition des coûts, décomposition des coûts ou classification des coûts. 

La segmentation des groupes de coûts a plusieurs synonymes dans les environnements de fabrication, comme répartition des coûts, décomposition des coûts ou classification des coûts. La segmentation des groupes de coûts a différents objectifs. Voici quelques exemples :

-   Elle peut segmenter les coûts pour différents types de matériaux, tels que les ingrédients et le matériel d'emballage pour un produit en conserve, sur la base des groupes de coûts qui sont attribués aux articles.
-   Elle peut segmenter les coûts pour différents types de ressources opérationnelles, tels que les différents types de mains-d'œuvre ou de machines, sur la base des groupes de coûts qui sont attribués aux catégories de coûts associées aux ressources opérationnelles et aux opérations de gamme.
-   Elle peut segmenter les coûts pour le temps de réglage et le temps d'exécution des opérations de gamme, sur la base des groupes de coûts qui sont affectés aux catégories de coûts associées aux opérations de gamme.
-   Elle peut segmenter les coûts pour différents types de frais généraux, tels que les frais généraux liés à la main-d'œuvre et aux machines, sur la base des groupes de coûts qui sont attribués aux coûts indirects dans le paramétrage de la feuille des coûts.
-   Elle peut servir de base pour le calcul de plusieurs types de frais généraux de fabrication dans le paramétrage de la feuille d'évaluation des coûts. Ces frais généraux peuvent inclure différents types de frais généraux associés aux informations de gamme relatives aux ressources opérationnelles ou aux informations relatives au temps de réglage et d'exécution. Les frais généraux de fabrication peuvent également être associés aux contributions des coûts des matières du composant, reflétant une philosophie de production au plus juste qui élimine le besoin d'informations sur la gamme.

La segmentation des groupes de coûts s'applique aux coûts calculés d'un article fabriqué, que ces coûts soient basés sur les coûts standard ou les coûts planifiés. La page **Synthèse** affiche cette segmentation par groupe de coûts, par niveau ou les deux. 

La possibilité de conserver la segmentation des groupes de coûts sur plusieurs niveaux dans une structure de produit est appelée *fractionnement*. Le fractionnement s'applique uniquement aux articles fabriqués qui utilisent un modèle de stock de coût standard. Si le fractionnement n'est pas utilisé, le coût d'un composant fabriqué est traité comme une contribution des coûts des matières. Le paramètre de stock pour la répartition des coûts par sous-compte indique que la segmentation des groupes de coûts sera retenue à travers plusieurs niveaux dans les calculs des coûts standard, alors que si aucun paramètre n'est choisi, la segmentation des groupes de coûts ne s'applique qu'à un seul niveau de calcul. Par exemple, la page **Repositionnement des coûts par groupe de coûts** affiche la segmentation des groupes de coûts sur plusieurs niveaux pour les articles de coûts standard. 

La segmentation des groupes de coûts peut également s'appliquer aux écarts pour un article de coût standard. Un deuxième paramètre de stock définit si les écarts sont déterminés par groupe de coûts ou simplement récapitulés. 

Un type de groupe de coûts et un comportement pour une segmentation supplémentaire peuvent être affectés à un groupe de coûts.

-   **Type de groupe de coûts** − Chaque groupe de coûts peut se voir affecter un type de groupes de coûts pour indiquer que le groupe de coûts s'applique au matériel direct, à la fabrication directe ou à la sous-traitance directe, ou pour le désigner comme étant indirect ou indéterminé. Un groupe de coûts désigné comme faisant partie du matériel direct peut être affecté aux articles. Un groupe de coûts de la fabrication directe peut être affecté aux catégories de coûts. Un groupe de coûts de sous-traitance directe peut être affecté à un type de produit de service, pour vous permettre de classer les coûts associés à l'achat de service en activités de sous-traitance. Un groupe de coûts indirects peut être affecté aux coûts indirects pour les surcharges ou les taux. Un groupe de coûts indéterminé peut être affecté aux articles, aux catégories de coûts ou aux coûts indirects. L'affectation d'un type de groupe de coûts a différents objectifs. Premièrement, elle offre la possibilité d'affecter un groupe de coûts et d'afficher la liste des groupes de coûts applicables. Deuxièmement, elle offre une segmentation supplémentaire pour la génération d'états. Troisièmement, elle peut servir à l'affectation de comptes généraux pour les écarts.
-   **Comportement** − Un comportement peut éventuellement être affecté à chaque groupe de coûts pour indiquer que le groupe de coûts s'applique aux coûts fixes ou variables. Un groupe de coûts avec la valeur null pour le comportement est traité comme des coûts variables. L'affectation d'un comportement sert uniquement à la génération d'états. Par exemple, les coûts peuvent être affichés avec la segmentation de coûts fixes et variables sur la feuille d'évaluation des coûts et dans la page**Repositionnement des coûts par groupe de coûts**. Si vous affectez un pourcentage de paramétrage de profit à chaque groupe de coûts, le calcul de nomenclature définit un prix de vente suggéré basé sur une approche coût plus majoration.





