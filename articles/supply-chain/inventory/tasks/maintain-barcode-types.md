---
title: Tenir à jour les types de codes-barres
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
ms.openlocfilehash: 052311e15aeb20b927cbed217a2bda600dad60a5
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345648"
---
# <a name="maintain-bar-code-types"></a>Tenir à jour les types de codes-barres

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l’état de la liste de prélèvements. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées. Ces tâches sont généralement effectuées par un responsable de l’entrepôt.

1. Accédez à **Codes-barres**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Paramétrage des codes-barres**, tapez une valeur.
1. Tapez une valeur dans le champ **Description**.
1. Sélectionnez une option dans le champ **Type de code-barres**.
    * Si vous utilisez USMF, vous pouvez sélectionner Code 39.  
1. Entrez un nombre dans le champ **Taille**.
1. Dans le champ **Longueur maximale**, entrez un nombre.
1. Sélectionnez **Enregistrer**.
1. Fermez la page.
1. Accédez à **Paramètres de gestion des stocks et des entrepôts**.
1. Dans le champ **Paramétrage des codes-barres**, saisissez ou sélectionnez une valeur.
    * Sélectionnez le paramétrage des codes-barres que vous avez créé précédemment, mais gardez à l’esprit que le format de code-barres doit correspondre au format de l’identificateur unique du type d’enregistrement utilisé dans le processus. Par exemple, pour les parcours de prélèvement, le format de code-barres doit correspondre au format de la référence du parcours de prélèvement, qui est généralement une souche de numéros.  
1. Sélectionnez **Enregistrer**.
1. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]