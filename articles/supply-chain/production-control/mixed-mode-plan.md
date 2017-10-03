---
title: "Planification de mode mixte - combiner un approvisionnement discret, basé sur les processus et le lean manufacturing"
description: "Cet article fournit des informations sur la planification de mode mixte. Dans la planification de mode mixte, vous pouvez modéliser la chaîne d'approvisionnement selon le flux des matières. Microsoft Dynamics 365 for Finance and Operations garantit que le flux des matières suit vos modèles, indépendamment de la stratégie d'approvisionnement sélectionnée (kanbans, ordres de fabrication, commandes fournisseur, lots de commandes, ou ordres de transfert)."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 9dbbe540c919d27bafcc10614f308e5b6ba313f1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Planification de mode mixte - combiner un approvisionnement discret, basé sur les processus et le lean manufacturing

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur la planification de mode mixte. Dans la planification de mode mixte, vous pouvez modéliser la chaîne d'approvisionnement selon le flux des matières. Microsoft Dynamics 365 for Finance and Operations garantit que le flux des matières suit vos modèles, indépendamment de la stratégie d'approvisionnement sélectionnée (kanbans, ordres de fabrication, commandes fournisseur, lots de commandes, ou ordres de transfert). 

Vous pouvez sélectionner votre stratégie globale pour fournir un produit, indépendamment de la structure de produit.  

Par exemple, vous pouvez disposer du contrôle de kanban au niveau de l'assemblage, où les matières sont fournies à la zone d'assemblage par les ordres de fabrication, les kanbans, les transferts, les lots de commandes, ou toute combinaison appropriée pour les caractéristiques de votre chaîne d'approvisionnement, tout en conservant une visibilité complète des approvisionnements. Cette capacité permet de bénéficier de processus optimisés de chaîne d'approvisionnement et d'une visibilité améliorée de votre chaîne d'approvisionnement.  

La granularité des stratégies d'approvisionnement utilisées dans le calcul PDP/MRP dépend des dimensions de stockage qui sont activées en tant que dimensions de couverture. Pour activer le calcul PDP/MRP de sorte à contrôler le réapprovisionnement et l'approvisionnement de différents types d'emplacements (par exemple, en séparant l'atelier de production pour différentes unités de production, ou en séparant différents types d'entrepôts de matières et de produits finis), nous vous recommandons d'activer Site et Entrepôt en tant que dimensions de couverture. Sinon, Entrepôt peut être omis en tant que dimension de couverture. Dans ce cas, lorsque vous utilisez la gestion avancée des entrepôts, tous les mouvements à l'intérieur d'un entrepôt sont contrôlés par le travail d'entrepôt, alors que tous les mouvements sur plusieurs entrepôts peuvent être contrôlés par les kanbans de prélèvement.

## <a name="supply-policies"></a>Stratégies d'approvisionnement
Le mode de planification mixte de Finance and Operations contrôle comment un produit est fourni et, en fonction de l'approvisionnement, la façon dont les besoins déduits (consommation d'articles d'une \[nomenclature\]) sont émis. En fonction du type de commande, le système fournit automatiquement les matériaux pour répondre aux besoins.  

Les stratégies d'approvisionnement peuvent être définies au niveau du produit ou à n'importe quel niveau de granularité prenant en charge vos besoins. Vous définissez la granularité des stratégies d'approvisionnement sur la page **Paramètres de commande par défaut**.  

Les stratégies d'approvisionnement peuvent être contrôlées par produit, par dimensions d'article (configuration, couleur et taille), par site et par entrepôt. Ce paramétrage est effectué sur la page **Couverture de l'article**.  

Le type de commande par défaut contrôle ce que la planification de commandes génère.  

Indépendamment de la modélisation de la chaîne d'approvisionnement, Finance and Operations prend en charge votre combinaison de stratégies d'approvisionnement. Vous pouvez avoir des ordres de fabrication qui sont originaires des kanbans. Sinon, vous pouvez avoir un lot de commandes qui nécessite un produit fourni par les transferts ou par les kanbans.  

Finance and Operations garantit que le flux des matières suit le modèle.  

L'entrepôt de prélèvement des matières est affecté dynamiquement au moment de l'exécution, une fois la stratégie d'approvisionnement définie.  

Généralement, les kanbans ne sont pas créés pour des dates futures, car le cycle de vie d'un kanban est court. Pour conserver une visibilité complète de la chaîne d'approvisionnement, nous avons introduit le nouveau concept de planification de « kanban prévisionnel », utilisé pour calculer les besoins déduits et permettant de garantir que les besoins sont basés sur l'approvisionnement selon la même logique utilisée lorsque le kanban réel est créé.  

La même est logique est présente pour tous les autres types de stratégie d'approvisionnement. Par conséquent, la planification à long terme des matières est basée sur la même logique que vous prévoyez d'exécuter avec les commandes réelles une fois que la production et l'approvisionnement sont approuvés.

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a>Stratégie d'approvisionnement croisée de répartition des matières – Consommation de ressources dans les nomenclatures
La consommation de ressources est une fonction importante. La consommation de ressources active un entrepôt de prélèvement des matières à sélectionner dynamiquement, en fonction de la stratégie d'approvisionnement (type de commande), et facilite également la maintenance des données de base.  

La consommation de ressources exige que l'entrepôt d'où les matières sont prélevées soit affecté en fonction de la manière dont le produit est fourni. En d'autres termes, au moment de l'exécution, le système recherche les ressources qui doivent être utilisées pour la fabrication. En fonction de ces ressources, le système recherche alors l'entrepôt de prélèvement.  

Pour un travail qui est indépendant d'une stratégie d'approvisionnement, vous n'êtes pas obligé de modifier les informations de la nomenclature si l'approvisionnement est modifié. Pour les modifications ponctuelles, Finance and Operations garantit que les matières sont originaires de l'entrepôt approprié.

## <a name="process-manufacturing--the-production-type"></a>Production par processus – Le type de production
Pour une flexibilité complète en mode mixte, nous vous recommandons d'utiliser des nomenclatures de type production pour tous les produits. Vous pouvez alors utiliser des ordres de fabrication, des kanbans, des ordres de transfert ou des commandes fournisseur pour fournir un produit. Pour la production par processus, vous devez utiliser un type de production **Formule**, **Coproduit**, **Sous-produit** ou **Élément de planification**. Les kanbans et les ordres de fabrication ne peuvent pas être utilisées pour ces types de production.



