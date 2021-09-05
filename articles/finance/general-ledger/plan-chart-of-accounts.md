---
title: Plan de comptes
description: Cette rubrique fournit des informations vous permettant de planifier le plan de comptes de votre organisation.
author: aprilolson
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4a5c0d758ecacce6433b13a2b2044d2417d018
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2021
ms.locfileid: "7403863"
---
# <a name="plan-your-chart-of-accounts"></a>Plan de comptes

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations vous permettant de planifier le plan de comptes de votre organisation.

Pour suivre et tenir à jour les informations financières dans une organisation, vous pouvez paramétrer un plan de comptes. Un plan de comptes est un ensemble de comptes qui définit une structure financière. Pour effectuer un suivi approfondi des transactions dans ces comptes, vous pouvez ajouter des segments. Ces segments sont appelés des dimensions financières. Par exemple, un compte de dépenses peut inclure les dimensions financières nommées Département, Centre de coûts et Objectif. Des règles définies par l’utilisateur déterminent l’association des dimensions financières aux comptes principaux et aux autres dimensions financières, ainsi que les modalités de saisie des transactions. Ces règles définies par l’utilisateur sont désignées comme des structures de compte et des règles avancées.

Le plan de comptes est une liste structurée des comptes généraux d’une entité juridique. La liste permet de préparer les états financiers pour les administrations et les propriétaires. Les comptes sont d’abord regroupés en types de comptes, puis rassemblés dans de plus grandes catégories. Au niveau le plus général, les comptes sont regroupés par coûts et produits (comptes d’exploitation) et actifs et passifs (comptes de bilan).

Un plan de comptes peut être partagé et utilisé par les entités juridiques d’une organisation. Le plan de comptes qui est utilisé par une entité juridique est défini sur la page **Comptabilité**.

Voici des facteurs dont vous devez tenir compte lorsque vous planifiez la structure du plan de comptes pour votre organisation :

- les conditions de génération d’états du pays ou de la région où est basée la société ;
- les conditions de génération d’états de votre entité juridique ;
- le degré de spécification requis, à la fois pour les organisations externes et votre organisation.

Vous créez le plan de comptes dans la page **Plan de comptes**. Vous pouvez créer les comptes principaux à partir de la page **Plan de comptes** ou de la page **Comptes principaux**. Vos comptes principaux ne doivent pas utiliser de caractères spéciaux utilisés comme séparateurs de plan de comptes. Sinon, vous pouvez rencontrer de l’instabilité, ou vous pouvez toujours avoir à utiliser les recherches ou la boîte de dialogue lorsque vous entrez des combinaisons de comptes et de dimensions. Pour plus d’informations, voir [Créer un compte principal](tasks/create-main-account.md).

> [!NOTE]
> Dans Dynamics 365 for Finance and Operations version 8.0 (avril 2018), vous pouvez modifier le séparateur de plan de comptes sur la page **Paramètres de comptabilité**.

Il est préférable de lier les comptes principaux aux catégories de compte principal, afin de pouvoir tirer profit des états financiers par défaut sans devoir apporter des modifications. Par conséquent, vous pouvez concevoir et tenir à jour les états plus rapidement et plus facilement.

Vous créez des structures de compte sur la page **Configurer les structures de compte**. Les structures de compte définissent les combinaisons valides. Ces combinaisons, associées aux comptes principaux, forment un plan de comptes. Pour plus d’informations, voir [Créer des structures de compte](tasks/create-account-structures.md).

**Remplacements des entités juridiques**

Seuls certains comptes principaux sont valides pour toutes les entités juridiques et certains comptes principaux peuvent être appropriés uniquement pour une période spécifique. Dans ce scénario, vous pouvez utiliser la section **Remplacements des entités juridiques** pour identifier les sociétés pour lesquelles le compte principal doit être suspendu, le propriétaire et la période d’activité de la dimension. Les remplacements au niveau partagé ne peuvent pas être plus restrictifs que les remplacements au niveau de l’entité juridique.

Pour plus d’informations, voir les rubriques suivantes :

- [Dimensions financières](financial-dimensions.md)
- [Créer et affecter des structures de règle avancées](tasks/create-assign-advanced-rule-structures.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
