---
title: "Clôture de la comptabilité en fin de période"
description: "Cette rubrique décrit les tâches qui sont généralement effectuées lors de l&quot;exécution d&quot;une clôture de période pour la comptabilité."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 81d687cc16ef43442c8c1c166cc6f0d8b171e28f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="close-the-general-ledger-at-period-end"></a>Clôture de la comptabilité en fin de période

[!include[banner](../includes/banner.md)]


Cette rubrique décrit les tâches qui sont généralement effectuées lors de l'exécution d'une clôture de période pour la comptabilité. 

Dans la comptabilité, vous pouvez exécuter les procédures de clôture pour une période ou année. Les procédures de clôture préparent le système pour une nouvelle période. Pour préparer le système pour une année, vous devez exécuter le processus de clôture de fin d'exercice. Chaque organisation a différents processus et étapes qu'elle effectue pour la fin d'une période. Voici quelques étapes facultatives pour les fins de période :

-   Complétez toutes les tâches de tous les autres modules, tels que Comptabilité client Comptabilité fournisseur et Stock.
-   Vérifiez que tous les journaux sont validés.
-   Exécutez la réévaluation des comptes en devises pour générer tous les montants de profit non réalisé ou de perte.
-   Réglez les transactions pour chaque compte général.
-   Traitez toutes les répartitions demandées.
-   Validez manuellement les ajustements de fin de période.
-   Journalisez les transactions, et examinez l'état **Journal comptable**.
-   Exécutez une consolidation à l'aide d'une société de consolidation ou des états financiers.
-   Générez des tableaux d'analyse de période de fin à l'aide des états financiers.
-   Définissez les périodes comptables sur **En attente**, afin qu'aucune autre validation ne se produise. Vous pouvez également limiter une période à un groupe d'utilisateurs spécifique pendant que les activités de période de fin ont lieu, pour un meilleur contrôle. Il n'est pas recommandé de définir des périodes sur **Clôturé définitivement**, car vous ne pouvez pas rouvrir une période clôturée.

L'espace de travail Clôture de période comptable peut être utilisé pour organiser et suivre les tâches requises pour différents processus de fin de période. Reportez-vous aux rubriques [Espace de travail de clôture de période comptable](financial-period-close-workspace.md) et [Clôture de fin d'exercice](Year-end-close.md) pour plus d'informations. 






