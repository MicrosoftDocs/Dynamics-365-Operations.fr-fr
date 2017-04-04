---
title: "Planification en mode mixte - Permet de combiner discret, le processus, et l&quot;accès au plus juste"
description: "Cet article fournit des informations sur la planification de mode mixte. Dans la planification de mode mixte, vous pouvez modéliser la chaîne d&quot;approvisionnement selon le flux des matières. Microsoft Dynamics 365 pour les opérations garantit que les flux des matières suit vos modèles, indépendamment de la stratégie d&quot;approvisionnement sélectionnée (des kanbans, des ordres de fabrication, des commandes fournisseur, des lots de commandes, ou les ordres de transfert)."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d635421112f6d1e79a47090de3ffc4178b36b132
ms.lasthandoff: 03/31/2017


---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Planification en mode mixte - Permet de combiner discret, le processus, et l'accès au plus juste

Cet article fournit des informations sur la planification de mode mixte. Dans la planification de mode mixte, vous pouvez modéliser la chaîne d'approvisionnement selon le flux des matières. Microsoft Dynamics 365 pour les opérations garantit que les flux des matières suit vos modèles, indépendamment de la stratégie d'approvisionnement sélectionnée (des kanbans, des ordres de fabrication, des commandes fournisseur, des lots de commandes, ou les ordres de transfert). 

Vous pouvez sélectionner votre stratégie globale pour fournir un produit, indépendamment de la structure de produit.  

Par exemple, vous pouvez disposer du contrôle de kanban au niveau de l'assemblage, où les matières sont fournies à la zone d'assemblage par les ordres de fabrication, les kanbans, les transferts, les lots de commandes, ou toute combinaison appropriée pour les caractéristiques de votre chaîne d'approvisionnement, tout en conservant une visibilité complète des approvisionnements. Cette capacité permet de bénéficier de processus optimisés de chaîne d'approvisionnement et d'une visibilité améliorée de votre chaîne d'approvisionnement.  

La granularité des stratégies d'approvisionnement utilisées dans le calcul PDP/MRP dépend des dimensions de stockage qui sont activées en tant que dimensions de couverture. Pour activer le calcul PDP/MRP de sorte à contrôler le réapprovisionnement et l'approvisionnement de différents types d'emplacements (par exemple, en séparant l'atelier de production pour différentes unités de production, ou en séparant différents types d'entrepôts de matières et de produits finis), nous vous recommandons d'activer Site et Entrepôt en tant que dimensions de couverture. Sinon, Entrepôt peut être omis en tant que dimension de couverture. Dans ce cas, lorsque vous utilisez la gestion avancée des entrepôts, tous les mouvements à l'intérieur d'un entrepôt sont contrôlés par le travail d'entrepôt, alors que tous les mouvements sur plusieurs entrepôts peuvent être contrôlés par les kanbans de prélèvement.

## <a name="supply-policies"></a>Stratégies d'approvisionnement
Dynamics 365 pour les contrôles mixés par opérations de planification de mode comment un produit est fourni et, selon l'approvisionnement, la manière dont les besoins déduits (consommation d'articles d'une nomenclature\]\[de nomenclature) sont émis. En fonction du type de commande, le système fournit automatiquement les matériaux pour répondre aux besoins.  

Les stratégies d'approvisionnement peuvent être définies au niveau du produit ou à n'importe quel niveau de granularité prenant en charge vos besoins. Vous définissez la granularité des stratégies d'approvisionnement sur la page **Paramètres de commande par défaut**.  

Les stratégies d'approvisionnement peuvent être contrôlées par produit, par dimensions d'article (configuration, couleur et taille), par site et par entrepôt. Ce paramétrage est effectué sur la page **Couverture de l'article**.  

Le type de commande par défaut contrôle ce que la planification de commandes génère.  

Indépendamment de la configuration de la chaîne d'approvisionnement est modelée, Dynamics 365 pour les opérations prend en charge le mélange des stratégies d'approvisionnement. Vous pouvez avoir des ordres de fabrication qui sont originaires des kanbans. Sinon, vous pouvez avoir un lot de commandes qui nécessite un produit fourni par les transferts ou par les kanbans.  

Dynamics 365 pour les opérations garantit que les flux des matières suit le modèle.  

L'entrepôt de prélèvement des matières est affecté dynamiquement au moment de l'exécution, une fois la stratégie d'approvisionnement définie.  

Généralement, les kanbans ne sont pas créés pour des dates futures, car le cycle de vie d'un kanban est court. Pour conserver une visibilité complète de la chaîne d'approvisionnement, nous avons introduit le nouveau concept de planification de « kanban prévisionnel », utilisé pour calculer les besoins déduits et permettant de garantir que les besoins sont basés sur l'approvisionnement selon la même logique utilisée lorsque le kanban réel est créé.  

La même est logique est présente pour tous les autres types de stratégie d'approvisionnement. Par conséquent, la planification à long terme des matières est basée sur la même logique que vous prévoyez d'exécuter avec les commandes réelles une fois que la production et l'approvisionnement sont approuvés.

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a>De matières de répartition stratégie crosssupply – consommation de ressources sur les nomenclatures
La consommation de ressources est la fonction importante. La consommation de ressources active un entrepôt de prélèvement des matières à sélectionner dynamiquement, en fonction de la stratégie d'approvisionnement (type de commande), et facilite également la maintenance des données de base.  

La consommation de ressources exige que l'entrepôt d'où les matières sont prélevées soit affecté en fonction de la manière dont le produit est fourni. En d'autres termes, au moment de l'exécution, le système recherche les ressources qui doivent être utilisées pour la fabrication. En fonction de ces ressources, le système recherche alors l'entrepôt de prélèvement.  

Pour un travail qui est indépendant d'une stratégie d'approvisionnement, vous n'êtes pas obligé de modifier les informations de la nomenclature si l'approvisionnement est modifié. Pour les modifications ad hoc, Dynamics 365 pour les opérations garantit que les matières sont originaires de l'entrepôt vers la droite.

## <a name="process-manufacturing--the-production-type"></a>Production par processus – Le type de production
Pour la flexibilité complète en mode mixte, nous vous recommandons d'utiliser des nomenclatures de type de production pour tous les produits. Vous pouvez ensuite utiliser les ordres de fabrication, des kanbans, les ordres de transfert, ou fournisseur pour fournir un produit. Pour la production par processus, vous devez utiliser un type de production **Formule**, **Coproduit**, **Sous-produit** ou **Élément de planification**. Les kanbans et les ordres de fabrication ne peuvent pas être utilisées pour ces types de production.


