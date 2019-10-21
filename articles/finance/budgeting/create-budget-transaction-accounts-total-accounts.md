---
title: Créer un budget à partir des comptes de transactions et des comptes de type Total
description: Cet article fournit une vue d'ensemble du processus de création des budgets en fonction des comptes de type total. Il décrit également comment activer le contrôle budgétaire des comptes de type total, si le contrôle budgétaire est requis.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f60963bee790737c85161dff03278df0572e3abc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177757"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Créer un budget à partir des comptes de transactions et des comptes de type Total

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d'ensemble du processus de création des budgets en fonction des comptes de type total. Il décrit également comment activer le contrôle budgétaire des comptes de type total, si le contrôle budgétaire est requis.

Les documents d'écriture plan budgétaire et registre budgétaire permettent de procéder à la budgétisation sur les comptes principaux dont le type de compte est **Total**. Les chiffres réels peuvent être validés uniquement dans les comptes principaux transactionnels. 

Pour le processus périodique **Générer le plan budgétaire à partir de la comptabilité**, dans l'onglet **Source**, vous pouvez spécifier le type de compte principal **Total** comme critère. Dans ce cas, chaque compte principal de type Total est inclus dans le plan budgétaire cible ; le montant sera égal au montant total de la plage des comptes principaux sélectionnés. 

Vous pouvez activer le contrôle budgétaire pour les comptes principaux de type **Total**. Cette fonction est prise en charge via l'utilisation des groupes budgétaires. Pour chaque compte principal de type Total, le budget qui doit être contrôlé pour un groupe budgétaire doit être créé dans la page **Configuration du contrôle budgétaire**. Les critères que vous spécifiez doivent inclure le compte principal de type Total et la plage de comptes. Pour accélérer le processus de création de groupes budgétaires, vous pouvez tirer profit de l'entité de données Groupes de contrôle budgétaire. 

Lorsqu'un budget est utilisé dans la génération d'états, par exemple, dans un tableau d'analyse, la somme de budget pour le compte de type Total comprend les montants suivants :

-   Les budgets créés à partir de chaque compte général de transaction dans l'intervalle du compte de type total.
-   le montant du budget entré directement sur le compte global.

Par conséquent, vous pouvez créer des budgets distincts pour les comptes de transactions les plus importants dans l'intervalle du compte de type Total et ajouter le montant de budget disponible au compte de type Total.



