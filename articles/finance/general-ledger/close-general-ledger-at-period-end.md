---
title: Clôture de la comptabilité en fin de période
description: Cet article décrit les tâches qui sont généralement effectuées lors de l’exécution d’une clôture de période pour la comptabilité.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42a5df1cd1a73462c93012b26f9b9b5c1631f2ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878039"
---
# <a name="close-the-general-ledger-at-period-end"></a>Clôture de la comptabilité en fin de période

[!include [banner](../includes/banner.md)]

Cet article décrit les tâches qui sont généralement effectuées lors de l’exécution d’une clôture de période pour la comptabilité. 

Dans la comptabilité, vous pouvez exécuter les procédures de clôture pour une période ou année. Les procédures de clôture préparent le système pour une nouvelle période. Pour préparer une nouvelle année, vous devez exécuter le processus de clôture de fin d’exercice. Chaque organisation a différents processus et étapes qu’elle effectue pour la fin d’une période. Voici quelques étapes facultatives pour les fins de période :

-   Complétez toutes les tâches de tous les autres modules, tels que Comptabilité client Comptabilité fournisseur et Stock.
-   Vérifiez que tous les journaux sont validés.
-   Exécutez la réévaluation des comptes en devises pour générer tous les montants de profit non réalisé ou de perte.
-   Réglez les transactions pour chaque compte général.
-   Traitez toutes les répartitions demandées.
-   Validez manuellement les ajustements de fin de période.
-   Journalisez les transactions, et examinez l’état **Journal comptable**.
-   Exécutez une consolidation à l’aide d’une société de consolidation ou des états financiers.
-   Générez des tableaux d’analyse de période de fin à l’aide des états financiers.
-   Définissez les périodes comptables sur **En attente**, afin qu’aucune autre validation ne se produise. Vous pouvez également limiter une période à un groupe d’utilisateurs spécifique pendant que les activités de période de fin ont lieu, pour un meilleur contrôle. Il n’est pas recommandé de définir des périodes sur **Clôturé définitivement**, car vous ne pouvez pas rouvrir une période clôturée.

L’espace de travail **Clôture de période comptable** peut être utilisé pour organiser et suivre les tâches requises pour différents processus de fin de période. 


Pour plus d’informations, voir les rubriques suivantes :
- [Espace de travail de clôture de période comptable](financial-period-close-workspace.md) 
- [Clôture de fin d’exercice](Year-end-close.md)  
- [Secteur de clôture de période comptable](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
