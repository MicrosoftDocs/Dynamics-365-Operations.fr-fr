---
title: Tenir à jour les types de code-barres
description: Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l’état de la liste de prélèvements.
author: perlynne
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 937384f14d88dafd537888d862ee1e363ea20626
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809516"
---
# <a name="maintain-barcode-types"></a>Tenir à jour les types de code-barres

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l’état de la liste de prélèvements. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées. Ces tâches sont généralement effectuées par un responsable de l’entrepôt.

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
    * Sélectionnez le paramétrage de code-barres que vous avez créé précédemment, mais gardez à l’esprit que le format de code-barres doit correspondre au format de l’identificateur unique du type d’enregistrement utilisé dans le processus. Par exemple, pour les parcours de prélèvement, le format de code-barres doit correspondre au format de la référence du parcours de prélèvement, qui est généralement une souche de numéros.  
12. Cliquez sur Enregistrer.
13. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]