---
title: "Mettre à jour les types de codes-barres"
description: "Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l'état de la liste de prélèvements."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45323206550d1b0ed66d89f4be7b995c60af63fc
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-bar-code-types"></a>Mettre à jour les types de codes-barres

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l'état de la liste de prélèvements. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées. Ces tâches sont généralement effectuées par un responsable de l'entrepôt.

1. Accédez à Codes-barres.
2. Cliquez sur Nouveau.
3. Dans le champ Paramétrage des codes-barres, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez une option dans le champ Type de code-barres.
    * Si vous utilisez USMF, vous pouvez sélectionner Code 39.  
6. Entrez un nombre dans le champ Taille.
7. Dans le champ Longueur maximale, entrez un nombre.
8. Cliquez sur Enregistrer.
9. Fermez la page.
10. Accédez à Paramètres de gestion des stocks et des entrepôts.
11. Dans le champ Paramétrage des codes-barres, saisissez ou sélectionnez une valeur.
    * Sélectionnez le paramétrage de code-barres que vous avez créé précédemment, mais gardez à l'esprit que le format de code-barres doit correspondre au format de l'identificateur unique du type d'enregistrement utilisé dans le processus. Par exemple, pour les parcours de prélèvement, le format de code-barres doit correspondre au format de la référence du parcours de prélèvement, qui est généralement une souche de numéros.  
12. Cliquez sur Enregistrer.
13. Fermez la page.

