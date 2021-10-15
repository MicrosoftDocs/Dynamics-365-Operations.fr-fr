---
title: Tenir à jour les types de codes-barres
description: Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l’état de la liste de prélèvements.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b689d1fc85d59ac87efa1903fd7122ae5ff011da
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571111"
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
1. Dans le champ **ID de masque**, spécifiez l'ID du masque de code à barres. Les masques de code-barres permettent de créer des codes-barres et d’identifier rapidement les codes-barres qui sont lus dans le système de point de vente (PDV). Pour plus de détails, voir [Configurer des masques de code à barres](../../../commerce/set-up-bar-code-masks.md).
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
