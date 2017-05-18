---
title: "Traiter les répartitions"
description: "Cet article fournit des informations sur les répartitions, les options pour les traiter dans Microsoft Dynamics 365 for Operations, et comment elles peuvent être utilisées dans la planification budgétaire. Les répartitions sont utilisées pour répartir les montants entre plusieurs combinaisons de compte général. Elles permettent de garantir que les dépenses ou le produit sont facturés pour l&quot;objet approprié dans la comptabilité."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f66414beeacafdbbe3b6f7bcba8481096636e025
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="process-allocations"></a>Traiter les répartitions

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les répartitions, les options pour les traiter dans Microsoft Dynamics 365 for Operations, et comment elles peuvent être utilisées dans la planification budgétaire. Les répartitions sont utilisées pour répartir les montants entre plusieurs combinaisons de compte général. Elles permettent de garantir que les dépenses ou le produit sont facturés pour l'objet approprié dans la comptabilité.

Microsoft Dynamics 365 for Operations fournit les fonctionnalités suivantes pour prendre en charge ce processus :

-   Répartir manuellement les montants de transaction à l'aide de l'action Fractionnement dans les répartitions comptables, ou en appliquant les modèles par défaut de dimension financière à un document. Pour plus d'informations, consultez [Répartitions comptables.](../accounts-payable/accounting-distributions.md)
-   Répartir automatiquement les montants des transactions selon des conditions de répartition définies sur le compte principal individuel. Les écritures de compte de répartition seront générées pour chaque journal en fonction du pourcentage et du compte général de destination à chaque fois qu'une écriture comptable répond aux critères définis comme compte général source.
-   Répartir automatiquement les soldes de comptabilité ou les montants fixes en fonction des règles de répartition comptable. Les règles de répartition comptable sont traitées sur une base périodique à l'aide des journaux de répartition. 

###  <a name="allocations-in-budget-planning"></a>Répartitions dans la planification budgétaire

Les règles de répartition comptable peuvent être utilisées pour les plans budgétaires. Lorsque vous utilisez des règles de répartition comptable dans la planification budgétaire, les règles de répartition fonctionnent de la même manière que dans la comptabilité, mais les données sources et les données de destination proviennent du plan budgétaire. Vous pouvez sélectionner manuellement les règles de répartition comptable à utiliser pour les plans budgétaires. Sinon, vous pouvez utiliser un programme de répartition qui s'exécute dans le cadre d'un processus de workflow.

> [!NOTE]
> Vous ne pouvez pas utiliser les règles de répartition comptable intersociétés pour la planification budgétaire.






