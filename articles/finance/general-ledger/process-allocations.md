---
title: Traiter les répartitions
description: Cet article fournit des informations sur les répartitions, les options pour les traiter dans Microsoft Dynamics 365 Finance, et comment elles peuvent être utilisées dans la planification budgétaire. Les répartitions sont utilisées pour répartir les montants entre plusieurs combinaisons de compte général. Elles permettent de garantir que les dépenses sont facturées pour l'objet approprié dans la comptabilité.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf889169357ea0598a3fe24b09a6eb565209b9c0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186346"
---
# <a name="process-allocations"></a>Traiter les répartitions

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les répartitions, les options pour les traiter, et comment elles peuvent être utilisées dans la planification budgétaire. Les répartitions sont utilisées pour répartir les montants entre plusieurs combinaisons de compte général. Elles permettent de garantir que les dépenses sont facturées pour l'objet approprié dans la comptabilité.

Les fonctionnalités suivantes prennent en charge le processus suivant :

-   Répartir manuellement les montants de transaction à l'aide de l'action Fractionnement dans les répartitions comptables, ou en appliquant les modèles par défaut de dimension financière à un document. Pour plus d'informations, consultez [Répartitions comptables.](../accounts-payable/accounting-distributions.md)
-   Répartir automatiquement les montants des transactions selon des conditions de répartition définies sur le compte principal individuel. Les écritures de compte de répartition seront générées pour chaque journal en fonction du pourcentage et du compte général de destination à chaque fois qu'une écriture comptable répond aux critères définis comme compte général source.
-   Répartir automatiquement les soldes de comptabilité ou les montants fixes en fonction des règles de répartition comptable. Les règles de répartition comptable sont traitées sur une base périodique à l'aide des journaux de répartition. 

###  <a name="allocations-in-budget-planning"></a>Répartitions dans la planification budgétaire

Les règles de répartition comptable peuvent être utilisées pour les plans budgétaires. Lorsque vous utilisez des règles de répartition comptable dans la planification budgétaire, les règles de répartition fonctionnent de la même manière que dans la comptabilité, mais les données sources et les données de destination proviennent du plan budgétaire. Vous pouvez sélectionner manuellement les règles de répartition comptable à utiliser pour les plans budgétaires. Sinon, vous pouvez utiliser un programme de répartition qui s'exécute dans le cadre d'un processus de workflow.

> [!NOTE]
> Vous ne pouvez pas utiliser les règles de répartition comptable intersociétés pour la planification budgétaire.




