---
title: Planifier votre plan de comptes
description: Cet article fournit des informations vous permettant de planifier le plan de comptes de votre organisation.
author: aprilolson
manager: AnnBe
ms.date: 01/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ad55dd57483de4351c8501c5e226180fc73606aa
ms.openlocfilehash: 3d2cdeaf2fdeb2f587f82c97249886fb8db49154
ms.contentlocale: fr-fr
ms.lasthandoff: 01/11/2018

---

# <a name="plan-your-chart-of-accounts"></a>Planifier votre plan de comptes

[!include[banner](../includes/banner.md)]


Cet article fournit des informations vous permettant de planifier le plan de comptes de votre organisation.

Pour suivre et tenir à jour les informations financières dans une organisation, vous pouvez paramétrer un plan de comptes. Un plan de comptes est un ensemble de comptes qui définit une structure financière. Pour suivre de façon plus approfondie les transactions dans ces comptes, vous pouvez ajouter des segments (appelés dimensions financières). Par exemple, un compte de dépenses peut inclure les dimensions financières nommées Département, Centre de coûts et Objectif. Des règles définies par l'utilisateur (appelées structures de compte et règles avancées), déterminent l'association des dimensions financières aux comptes principaux et aux autres dimensions financières, ainsi que les modalités de saisie des transactions. 

Le plan de comptes est une liste structurée des comptes généraux d'une entité juridique. La liste permet de préparer les états financiers pour les administrations et les propriétaires. Les comptes sont regroupés en types de comptes, puis rassemblés dans de plus grandes catégories. Au niveau le plus général, les comptes sont regroupés par coûts et produits (comptes d'exploitation) et actifs et passifs (comptes de bilan). 

Un plan de comptes peut être partagé et utilisé par les entités juridiques d'une organisation. Le plan de comptes qui est utilisé par une entité juridique est défini sur la page **Comptabilité**. 

Voici des facteurs dont vous devez tenir compte lorsque vous planifiez la structure du plan de comptes pour votre organisation :

-   les conditions de génération d'états du pays ou de la région où est basée la société ;
-   les conditions de génération d'états de votre entité juridique ;
-   le degré de spécification requis, à la fois pour les organisations externes et votre organisation.

Créez le plan de comptes dans la page **Plan de comptes**. Les comptes principaux peuvent être créés à partir de la page **Plan de comptes** ou de la page **Comptes principaux**. Vos comptes principaux ne doivent pas utiliser de caractères spéciaux utilisés comme séparateurs de plan de comptes. Si vous avez un caractère spécial qui est identique à votre séparateur de plan de comptes, il peut y avoir une instabilité, ou la nécessité de toujours utiliser des recherches ou le menu volant pour saisir le compte et les combinaisons de dimensions. Pour plus d'informations, voir [Créer un compte principal](tasks/create-main-account.md).


Il est préférable de lier les comptes principaux aux catégories de compte principal, afin de pouvoir tirer profit des états financiers par défaut sans devoir apporter des modifications. Par conséquent, vous pouvez concevoir et tenir à jour les états plus rapidement et plus facilement. 

Utilisez la page **Configurer les structures de compte** pour créer des structures de compte. Les structures de compte définissent les combinaisons valides. Les combinaisons, associées aux comptes principaux, forment un plan de comptes.  Pour plus d'informations, voir [Créer des structures de compte](tasks/create-account-structures.md).

**Remplacements des entités juridiques** 

Seuls certains comptes principaux sont valides pour toutes les entités juridiques et certaines peuvent être appropriées uniquement pour une période spécifique. Dans ce scénario, la section Remplacements des entités juridiques peut être utilisée pour identifier les sociétés pour lesquelles le compte principal doit être suspendu, le propriétaire et la période d'activité de la dimension. Les remplacements au niveau partagé ne peuvent pas être plus restrictifs que les remplacements au niveau de l'entité juridique.

Pour plus d'informations, voir les rubriques suivantes : [Dimensions financières](financial-dimensions.md)
[Créer et affecter des structures de règle avancées](tasks/create-assign-advanced-rule-structures.md)




